---
title: "Siebel ビジネス サービスに対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1ffd133d76b1f8cae3f1732e48f817fe4fb26b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-business-services-in-siebel"></a>Siebel ビジネス サービスに対する操作
Siebel ビジネス サービスは、Siebel の直接呼び出すことができるビジネス メソッドのコレクションです。 ビジネス コンポーネントとビジネス オブジェクトは、特定のデータと Siebel のテーブルに関連付けられているは、ビジネス サービスは、特定のタスクを実行するオブジェクトを呼び出します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェスのビジネス サービス メソッドのように操作名し、IN、OUT、および INOUT のパラメーターをサポートします。 たとえば、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェス、 **ATPRunCheck**操作としてメソッドです。 このメソッドが属する、 **ATP**ビジネス サービス。  
  
 特定の状態です、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel ビジネス サービスを使用しているときに。  
  
-   Siebel ビジネス サービス メソッドは、指定されたデータ型がない引数を受け取り、アダプターは、引数をテキストとして公開します。  
  
-   次の種類の Siebel ビジネス サービス メソッドの引数になります。  
  
    -   文字列 (xsd:string として公開)  
  
    -   数 (xsd として公開します 10 進数)。  
  
    -   日付 (時刻部分は 00時 00分: 00 に設定する必要がありますでパターン ファセットを示すの xsd:DateTime として公開)  
  
    -   階層 (xsd:string として公開)  
  
    -   統合オブジェクト (xsd:string として公開)  
  
     また、ビジネス サービス メソッドでは、引数に渡された値が、対応する型に準拠しているかどうかを確認します。 そのため、ビジネス サービス メソッドを受け入れるか、対応する引数の型に準拠していない値を返す場合、アダプターは例外をスロー可能性があります。 ビジネス サービス メソッドの呼び出しに成功しますが、アダプター スキーマの検証が失敗します。  
  
 詳細については。  
  
-   BizTalk Server を使用してサービスをビジネス上の操作を実行するを参照してください[呼び出すビジネス サービス メソッドを使用して BizTalk Server と Siebel アダプター](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)です。  
  
-   メッセージの構造と SOAP アクションのビジネス サービスでの操作を実行するを参照してください[ビジネス サービス操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md))。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)