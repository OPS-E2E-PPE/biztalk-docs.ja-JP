---
title: "構成情報 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], planning
- Call Rules shape [Orchestration Designer], configuring
ms.assetid: aa4924c6-4270-473b-aa0a-6d8b18375a39
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a35767815eaf7406a7baae5d9dccb833492287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-information"></a>構成情報
このトピックの内容を構成する方法を説明します、**ルールの呼び出し**図形です。  
  
## <a name="orchestration-variables-and-fact-types"></a>オーケストレーションの変数とファクトの種類  
 オーケストレーション内で、**ルールの呼び出し**図形が存在する、ポリシーで使用される型と一致する変数をする必要があります。 正しい型の変数がない場合、ポリシーに対して適切なパラメーターを提供できません。 あると仮定する**ルールの呼び出し**図形をオーケストレーションや CallMyRules、CallMyRules を使用して MyPolicy を呼び出す。 MyPolicy に .NET クラス MyClass が使用されている場合、オーケストレーションにも MyAssembly.MyClass 型の変数を作成する必要があります。 同様に、MyPolicy に**DataConnection**バインドの変数を作成する必要があります、 **Microsoft.RuleEngine.DataConnection**オーケストレーション内の型。  
  
 オーケストレーションに変数を作成し、さらに、これらの変数のインスタンスを作成する必要があります。 追加することでこれを行う、**式**図形をオーケストレーションにします。 前の例を使用して、インスタンスを作成、MyAssembly.MyClass のインスタンスと**DataConnection**インスタンス。 インスタンスを作成する、 **DataConnection**インスタンス、以下を実行できます。  
  
-   作成、 **SqlConnection**インスタンスし、して MySqlCon に割り当てます。  
  
-   作成、 **DataConnection**をインスタンス化し、dataConnection に割り当てます (の変数**DataConnection**型)、次のコード フラグメントで示すように。  
  
    ```  
    dataConnection = new Microsoft.RuleEngine.DataConnection("NameOfSqlDatabaseHere", "NameOfYourTableHere", MySqlCon);  
    ```  
  
> [!NOTE]
>  ファクトの種類と一致する変数があるない場合、これらの型は、パラメーターとしてでは表示されません、**ポリシー パラメーターの指定**リスト ボックスで、 **CallRules ポリシーの構成** ダイアログ ボックス。  
  
> [!NOTE]
>  オーケストレーション エンジンは、BRE ポリシーへのパラメーターとして指定したメッセージ変数を自動的に変換**TypedXmlDocument**オブジェクト、およびポリシーを実行する前に、ルール エンジンの作業メモリにアサートします。 このため、.NET やデータベース ファクトの場合とは異なり、TypedXmlDocument 型の変数を宣言する必要はありません。  
  
## <a name="message-type-and-document-type"></a>メッセージの種類とドキュメントの種類  
 確認する必要があります、 **DocumentType** (つまり、ビジネス ルール作成ツールで実装すると)、ビジネス ルールで使用される XML ノードのプロパティと同じ、 **MessageType**で定義されている XML ノード、オーケストレーション: と一致している必要があります、 **MessageType**メッセージまたはでルール エンジンに渡されるメッセージ部分の**ルールの呼び出し**図形です。  
  
 たとえば、BizTalk プロジェクトで、注文書 (PO) XML スキーマを定義する場合、 **MessageType**このスキーマに定義された**BTSProject.PO** (場合**BTSProject**は、名前空間または既定の名前空間を使用して、プロジェクト名)。  
  
 場合、 **\amount**要素、ルールの定義を削除する前にする必要がありますを変更するその**DocumentType**プロパティを**BTSProject.PO**プロパティ ウィンドウ. プロパティ ウィンドウをアクセスするには、スキーマ内の任意のノードを選択すると、 **XML スキーマ** タブで、ファクト エクスプ ローラー。 このスキーマはスキーマ内のすべての要素に適用されますが、永続化されません。 ビジネス ルール作成ツールを起動したり、スキーマを再度読み込んだときに、スキーマを再設定する必要があります。 これは、XML スキーマまたは XML スキーマから直接構築されたルールに基づいてボキャブラリを定義する場合に必要です。 これを行わない場合、ポリシーを実行できますが、**ルールの呼び出し**図形が正しく機能しないと、メッセージの種類に表示されません、**ポリシー パラメーターの指定**リスト ボックスで、 **[CallRules ポリシーの構成**] ダイアログ ボックス。