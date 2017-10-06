---
title: "手順 2: 在庫要求スキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5199b20a75b82e12ad76b96903538487a3128668
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-the-inventory-request-schema"></a>ステップ 2: 在庫要求スキーマの作成
![手順 5 の 2](../core/media/step-2of5.gif "Step_2of5")  
  
 **所要時間:** 7 分  
  
 **目標:**このステップでは、在庫補充メッセージのスキーマを定義します。  倉庫システムでは在庫の補充を要求するためにこのメッセージを送信します。  これはこのプロジェクトに対して作成する必要のある 2 つのスキーマのうちの 1 つです。  
  
 **目的:** XML は、構造体だけでなくおよび標準化されたマークアップ コードを使用して情報を識別しますが、スキーマを使用する機能も備えています。 スキーマとは、辞書のように機能し、他の XML ドキュメントによって参照として使用される XML ドキュメントです。 スキーマ コードは、XML 要素のスペルおよびこれらの要素で囲まれるデータの種類を定義します。 スキーマを使用することにより、プログラムでは XML ドキュメントを簡単に処理することができ、情報の構造と種類が正しいことを保証できます。  
  
## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  
  
-   この手順を開始する前に行う必要があります[手順 1: EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)です。  
  
## <a name="procedures"></a>手順  
 [手順 1: EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)、新しく作成した[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクト。  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ウィンドウを閉じた場合は、次の手順を使用してプロジェクトを開くことができます。  閉じていない場合は、「Visual Studio プロジェクトを開くには」の手順を省略できます。  
  
#### <a name="to-open-the-visual-studio-project"></a>Visual Studio プロジェクトを開くには  
  
1.  開始**Microsoft Visual Studio**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**開く**、クリックして**プロジェクト/ソリューション**です。  
  
3.  **プロジェクトを開く** ダイアログ ボックスを参照、 **C:\BTSTutorials\EAISolution\EAISolution.sln**ソリューション ファイル、およびクリック**開く**です。  
  
 次の手順では、在庫補充メッセージ用の新しいスキーマ ファイルをプロジェクトに追加します。  
  
#### <a name="to-add-a-new-schema-to-the-project"></a>新しいスキーマをプロジェクトに追加するには、次の操作を行います。  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。  
  
2.  **新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストールされたテンプレート**|をクリックして**スキーマ ファイル**をクリックし、**スキーマ**です。|  
    |**名前**|型**Request.xsd**です。|  
  
3.  **[追加]**をクリックします。 スキーマ ツリーと XSD ペインが表示されます。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のこの領域を、BizTalk エディターといいます。 また、ソリューション エクスプローラーでは、EAISchemas プロジェクトの下に新しいスキーマが表示されます。  
  
     ![BizTalk プロジェクトのさまざまな部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")  
  
#### <a name="to-add-elements-to-the-schema"></a>要素をスキーマに追加するには  
  
1.  スキーマ ツリーで、クリックして、**ルート**ノード。  
  
2.  値を変更、プロパティ ペインで、**ノード名**プロパティを`Request`、ENTER キーを押します。  
  
3.  スキーマ ツリー内を右クリックし、**要求**に**スキーマ ノードの挿入**、順にクリック**子レコード**です。  
  
4.  型`Header`子レコードとし、ENTER キーを押して新しい名前として。  
  
5.  に対して手順 3. および 4. を 2 番目の子を作成するレコードを繰り返して、**要求**ノード、名前を付けます`Items`です。  
  
6.  スキーマ ツリー内を右クリックし、**ヘッダー**に**スキーマ ノードの挿入**、順にクリック**子フィールド要素**です。  
  
7.  型`ReqID`要素、およびし、ENTER キーを押して新しい名前として。  
  
8.  手順 6 および 7 を 2 番目の子を作成するフィールドの要素を**ヘッダー**ノード、名前を付けます`OrderDate`です。  
  
9. スキーマ ツリー内を右クリックし、**項目**に**スキーマ ノードの挿入**、順にクリック**子レコード**です。  
  
10. 型`Item`子レコードとし、ENTER キーを押して新しい名前として。  
  
11. スキーマ ツリー内を右クリックし、**項目**ノード、し、次の子フィールド要素を追加します。  
  
    -   `Description`  
  
    -   `Quantity`  
  
    -   `UnitPrice`  
  
     完成した Request.xsd は、次の図のようになります。  
  
     ![ソリューション エクスプ ローラー、要求スキーマを持つ](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")  
  
 ノードをスキーマに追加するときは、そのプロパティの一連の既定値が提供されます。  これらは要件に基づいて構成する必要があります。  
  
#### <a name="to-configure-the-elements"></a>要素を構成するには  
  
1.  スキーマ ツリーで、クリックして**OrderDate**をオンにします。  
  
2.  プロパティ ウィンドウで、次のように変更します。**データ型**に**xs:dateTime**です。  
  
3.  手順 1. および 2. を繰り返して次のプロパティを構成します。  
  
    |要素|プロパティ|値|  
    |-------------|--------------|-----------|  
    |**[総計]**|**データ型**|**Xs:decimal**|  
    |**アイテム**|**Max Occurs します。**|**Unbounded**|  
    |**アイテム**|**Min Occurs します。**|**1**|  
    |**数量**|**データ型**|**xs:unsignedInt**|  
  
 スキーマは数多くの要素を持つことができますが、アプリケーションではデータ処理にその一部のみしか求められない場合があります。 コンピューターのリソースを節約するために、BizTalk サーバーでは各スキーマ要素を自動的に読み取りません。 BizTalk サーバーが特定の要素からデータを読み取るようにするには、BizTalk エディターを使用してその要素のプロパティを昇格することで、要素を識別する必要があります。  
  
 作成するオーケストレーション[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)は基にメッセージをルーティングするための GrandTotal フィールドです。  このため、GrandTotal フィールドを昇格する必要があります。  
  
#### <a name="to-promote-an-element"></a>要素を昇格するには  
  
1.  スキーマ ツリー内を右クリックして**GrandTotal**、をポイント**昇格**、クリックして**クイック昇格**です。  
  
2.  をクリックして**OK**プロパティ スキーマを追加することを確認します。  
  
3.  **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、倉庫の在庫補充メッセージのスキーマを定義しました。  
  
## <a name="next-steps"></a>次の手順  
 要求拒否メッセージのスキーマを定義します。  
  
## <a name="see-also"></a>参照  
 [手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)   
 [手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)   
 [手順 4: マップを作成します。](../core/step-4-create-the-map.md)   
 [手順 5: EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md)   
 [BizTalk エディターを使用してスキーマを作成します。](../core/creating-schemas-using-biztalk-editor.md)   
 [BizTalk メッセージ コンテキストのプロパティについて](../core/about-biztalk-message-context-properties.md)