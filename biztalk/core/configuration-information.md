---
title: 構成情報 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], planning
- Call Rules shape [Orchestration Designer], configuring
ms.assetid: aa4924c6-4270-473b-aa0a-6d8b18375a39
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9d58c810f4c0a01046d900f8654556f523f7a27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356484"
---
# <a name="configuration-information"></a>構成情報
このトピックでは、構成する方法を説明します、**ルールの呼び出し**図形。  
  
## <a name="orchestration-variables-and-fact-types"></a>オーケストレーションの変数とファクトの種類  
 オーケストレーションの場所、**ルールの呼び出し**図形が存在する、ポリシーで使用される型に一致する変数をいる必要があります。 正しい型の変数がない、ポリシーに適切なパラメーターを指定することはできません。 あると、**ルールの呼び出し**図形をオーケストレーションや CallMyRules、CallMyRules を使用して MyPolicy を呼び出す。 MyPolicy に .NET クラス MyClass を使用する場合は、オーケストレーションでも MyAssembly.MyClass 型の変数を作成する必要があります。 同様に、MyPolicy に**DataConnection**バインドの変数を作成する必要があります、 **Microsoft.RuleEngine.DataConnection**オーケストレーションの種類。  
  
 オーケストレーションで変数を作成、だけでなく、これらの変数のインスタンスを作成することも必要があります。 追加することでこれを行う、**式**図形をオーケストレーションにします。 前の例を使用して、MyAssembly.MyClass インスタンスを作成する必要があります、 **DataConnection**インスタンス。 インスタンス化する、 **DataConnection**インスタンス、以下を実行できます。  
  
-   作成、 **SqlConnection**インスタンスし、して MySqlCon に割り当てます。  
  
-   作成、 **DataConnection**をインスタンス化し、dataConnection に割り当てます (変数の**DataConnection**型) の次のコード フラグメントに示しますように。  
  
    ```  
    dataConnection = new Microsoft.RuleEngine.DataConnection("NameOfSqlDatabaseHere", "NameOfYourTableHere", MySqlCon);  
    ```  
  
> [!NOTE]
>  ファクトの種類と一致する変数がないの場合、これらの型は、パラメーターとしてでは表示されません、**ポリシー パラメーターの指定**リスト ボックスで、 **CallRules ポリシーの構成** ダイアログ ボックス。  
  
> [!NOTE]
>  オーケストレーション エンジンは、BRE ポリシーへのパラメーターとして指定したメッセージ変数を自動的に変換します**TypedXmlDocument**オブジェクト、およびポリシーを実行する前に、ルール エンジンの作業メモリにアサートします。 そのため、.NET やデータベース ファクトの場合と同様に、TypedXmlDocument 型の変数を宣言する必要はありません。  
  
## <a name="message-type-and-document-type"></a>メッセージの種類とドキュメントの種類  
 いることを確認する必要があります、 **DocumentType** (つまり、ビジネス ルール作成ツールで実装すると)、ビジネス ルールで使用される XML ノードのプロパティが同じ、 **MessageType**で定義されている XML ノードに対して、オーケストレーション: に一致する必要があります、 **MessageType**メッセージまたはルール エンジンに渡されるメッセージ部分の**ルールの呼び出し**図形。  
  
 たとえば、BizTalk プロジェクトで、注文書 (PO) XML スキーマを定義する場合、 **MessageType**このスキーマが定義されている**BTSProject.PO** (場合**BTSProject**が、名前空間または既定の名前空間を使用して、プロジェクト名)。  
  
 場合、 **\amount**要素、ルールの定義を削除する前にする必要がありますを変更するその**DocumentType**プロパティを**BTSProject.PO**プロパティ ウィンドウ. プロパティ ウィンドウをアクセスするには、スキーマ内の任意のノードが選択されている、 **XML スキーマ**ファクト エクスプ ローラー タブ。 この変更は、スキーマ内のすべての要素に対して適用されますが、スキーマに保存されていません。 ビジネス ルール作成ツールを起動するか、スキーマを再読み込みには、それをリセットする必要があります。 これは、機能は、XML スキーマまたは XML スキーマから直接構築されたルールに基づいてボキャブラリの定義に必要です。 これを行わない場合も、ポリシーを実行できますが、**ルールの呼び出し**図形が正しく機能しないと、メッセージの種類に表示されません、**ポリシー パラメーターの指定**リスト ボックスで、 **CallRules ポリシーの構成** ダイアログ ボックス。