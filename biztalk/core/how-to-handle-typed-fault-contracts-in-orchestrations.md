---
title: オーケストレーションでコントラクトの型指定されたエラーを処理する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- typed fault contracts [orchestrations]
- WCF services, orchestrations
- orchestrations, typed fault contracts
- orchestrations, WCF services
ms.assetid: 5a1a7d22-b0ff-4d09-bebf-4995229784b0
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a7643c4a39785018368572d721eed3ef6545c6b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a>オーケストレーション内の型指定されたエラー コントラクトを処理する方法
このトピックでは、オーケストレーション内から WCF サービスを使用する際に、型指定されたエラー コントラクトを処理する方法について説明します。 WCF サービスを使用している必要があります、オーケストレーションで型指定されたエラー例外を処理する、 **FaultContractAttribute**サービス操作に適用される以外の場合は、エラーをスローしてを使用してそのため、 **FaultException**\<T\> T が任意の有効なデータ コントラクトまたは WCF サービスからのシリアル化可能な型を指定できます。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a>オーケストレーション内の型指定されたエラー コントラクトを処理するには  
  
1.  Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクト、ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加 - \<***プロジェクト名***\>**   ダイアログ ボックスで、**テンプレート**セクションで、 **WCF の使用サービス**、クリックして**追加**です。  
  
3.  **BizTalk WCF サービス使用ウィザードへようこそ** ] ページで [ **次**します。  
  
4.  **メタデータ ソース**  ページで、 **Metadata Exchange (MEX) エンドポイント**, 、 をクリックし、 **次**します。  
  
5.  **メタデータ エンドポイント** ページで、Ws-metadata Exchange または Http-get を通じてダウンロードのメタデータを提供する実行中のサービスの URL を指定: http://localhost:8005 などです。 URL からメタデータ ドキュメントを取得するにはクリックして **取得**します。 実行中のサービスは、基本的な認証方式を使用したユーザーの資格情報を必要とする場合はクリックして **編集** を開くには、 **BizTalk WCF サービス使用ウィザード**  ダイアログ ボックスのユーザー名と実行中のサービスにアクセスするときに使用するパスワードを指定できます。 **[次へ]**をクリックします。  
  
6.  **WCF サービス メタデータの概要のインポート**  ページで、設定内容を確認します。 クリックして **戻る** に変更を加えます。 クリックして **インポート** BizTalk アイテムと、WCF サービスを使用するために使用されている型を作成します。  
  
7.  **BizTalk WCF サービス使用ウィザードを完了する** ] ページで [ **完了**します。  
  
8.  使用している WCF サービスが、次のエラー例外をスローするとします。  
  
    ```  
    throw new FaultException<MyOperationException>(divideException);  
    ```  
  
     送信ポートでのエラー操作には、型のメッセージが想定して **MyOperationException**, が WCF 応答メッセージには、エラー本文全体が含まれています。 そのため、抽出する必要があります、 **MyOperationException** 構成して、メッセージから、 **受信 BizTalk メッセージ本文** トランスポートのプロパティ ダイアログ ボックスでオプションです。 例を次に示します。  
  
    -   選択 **パス--本文のパスで見つかったコンテンツ**します。  
  
    -   本文のパス式を次のように設定します。  
  
        ```  
        /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
        ```  
  
    -   選択 **Xml** から、 **ノード エンコード** ボックスの一覧です。  
  
9. オーケストレーションで、1 つのスコープと 2 つの例外ハンドラを追加する必要があります。 1 つの例外ハンドラはのようなエラー処理 **MyOperationException** 前の例に示すように、その他の例外ハンドラーは、ジェネリックをキャッチするため、 **SOAPExceptions**します。  
  
## <a name="see-also"></a>参照  
 [WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)   
 [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)