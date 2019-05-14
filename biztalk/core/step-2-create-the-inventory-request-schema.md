---
title: 手順 2:在庫要求スキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa9ad9f-b815-4baf-8299-556869b8dde7
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0729083983aad67ad751aa3dd25d63c6a4c031f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392747"
---
# <a name="step-2-create-the-inventory-request-schema"></a>手順 2:在庫要求スキーマを作成します。
![手順 5 の 2](../core/media/step-2of5.gif "Step_2of5")  

 **所要時間:** 7 分  

 **目標:** この手順では、在庫補充メッセージのスキーマを定義します。  倉庫システムでは、在庫の補充を要求するためには、このメッセージを送信します。  これは、このプロジェクトを作成する必要があります、2 つのスキーマのいずれかです。  

 **目的:** XML は、構造体だけでなくと標準化されたマークアップ コードを使用して情報を識別しますが、スキーマを使用する機能もあります。 スキーマは、他の XML ドキュメントによってディクショナリのように機能し、参照として提供される XML ドキュメントです。 スキーマ コードは、XML 要素のスペルおよびこれらの要素で囲まれているデータの種類を定義します。 スキーマを使用して XML 文書化し、情報の種類と構造が正しいことを確実に処理するプログラムの簡単な方法を提供します。  

## <a name="prerequisites"></a>前提条件  
 このステップを開始する前に、以下の要件を確認してください。  

-   この手順を開始する前に行う必要があります[手順 1。EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)です。  

## <a name="procedures"></a>手順  
 [手順 1。EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)、新しく作成した[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクト。  閉じた場合、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウで、プロジェクトを開いて、次の手順を使用することができます。  それ以外の場合、"Visual Studio プロジェクトを開く"に、この手順を省略できます。  

#### <a name="to-open-the-visual-studio-project"></a>Visual Studio プロジェクトを開く  

1. 開始**Microsoft Visual Studio**します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト/ソリューション**。  

3. **プロジェクトを開く** ダイアログ ボックスを参照、 **C:\BTSTutorials\EAISolution\EAISolution.sln**ソリューション ファイル、およびクリック**オープン**します。  

   次の手順では、在庫補充メッセージ用のプロジェクトに新しいスキーマ ファイルを追加します。  

#### <a name="to-add-a-new-schema-to-the-project"></a>新しいスキーマをプロジェクトに追加するには  

1. ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。  

2. **新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作を行います。  


   |        プロパティ         |                   目的                   |
   |-------------------------|------------------------------------------------|
   | **インストール済みテンプレート** | クリックして**スキーマ ファイル**、 をクリックし、**スキーマ**します。 |
   |        **名前**         |             型**Request.xsd**します。              |


3. **[追加]** をクリックします。 スキーマ ツリーと XSD ペインが表示されます。 この領域[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk エディターと呼ばれます。 さらに、ソリューション エクスプ ローラーでは、EAISchemas プロジェクトの下に新しいスキーマが表示されます。  

    ![BizTalk プロジェクトのさまざまな部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")  

#### <a name="to-add-elements-to-the-schema"></a>スキーマの要素を追加するには  

1. スキーマ ツリーで、をクリックして、**ルート**ノード。  

2. プロパティ ペインでの値を変更、**ノード名**プロパティを`Request`、し、ENTER キーを押します。  

3. スキーマ ツリーで、右クリックし、**要求**に**スキーマ ノードの挿入**、 をクリックし、**子レコード**。  

4. 型`Header`として、新しいレコードの名前、子、ENTER キーを押します。  

5. 手順 3. および 4. を 2 つ目の子を作成するレコードを繰り返して、**要求**ノード、名前を付けます`Items`。  

6. スキーマ ツリーで、右クリックし、**ヘッダー**に**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**。  

7. 型`ReqID`要素、および、ENTER キーを押して新しい名前として。  

8. 手順 6 と 7 を作成する 2 つ目の子フィールド要素、**ヘッダー**ノード、名前を付けます`OrderDate`します。

9. 手順 6 と 7 を作成する 3 つ目の子フィールド要素、**ヘッダー**ノード、名前を付けます`GrandTotal`します。

10. スキーマ ツリーで、右クリックし、**項目**に**スキーマ ノードの挿入**、 をクリックし、**子レコード**。  

11. 型`Item`として、新しいレコードの名前、子、ENTER キーを押します。  

12. スキーマ ツリーで、右クリックし、**項目**ノードで、次の子フィールド要素を追加。  

    - `Description`  

    - `Quantity`  

    - `UnitPrice`  

      完成した Request.xsd は、次の図のようになります。  

      ![要求スキーマを使用して、ソリューション エクスプ ローラー](../core/media/solutionexplorerwiththerequestschema.gif "SolutionExplorerwiththeRequestSchema")  

    スキーマにノードを追加すると、それらのプロパティは既定値のセットが提供されます。  要件に基づいてそれらを構成する必要があります。  

#### <a name="to-configure-the-elements"></a>要素を構成するには  

1. スキーマ ツリーで、次のようにクリックします。 **OrderDate**をオンにします。  

2. プロパティ ペインで次のように変更します。**データ型**に**xs:dateTime**します。  

3. 1 と 2 は、次のプロパティを構成する手順を繰り返します。  

   |要素|プロパティ|値|  
   |-------------|--------------|-----------|  
   |**[総計]**|**[データ型]**|**Xs:decimal**|  
   |**アイテム**|**Max Occurs します。**|**無制限**|  
   |**アイテム**|**Min Occurs します。**|**1**|  
   |**数量**|**[データ型]**|**xs:unsignedInt**|  

   スキーマでは、多くの要素を使用できますが、アプリケーションは、データ処理のうちのいくつかを使用することのみ必要があります。 コンピューター リソースを保存するには、BizTalk Server は、各スキーマ要素を自動的に読み取りますしません。 BizTalk Server の特定の要素からデータを読み取る場合は、プロパティを昇格する BizTalk エディターを使用して、その要素を識別する必要があります。  

   オーケストレーション内に作成する[レッスン 2。ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)メッセージをルーティングするための GrandTotal フィールドに基づきます。  したがって、GrandTotal フィールドで昇格する必要があります。  

#### <a name="to-promote-an-element"></a>要素を昇格するには  

1.  スキーマ ツリーで、右クリックして**GrandTotal**、 をポイント**昇格**、 をクリックし、**クイック昇格**します。  

2.  をクリックして**OK**プロパティ スキーマを追加することを確認します。  

3.  **[ファイル]** メニューの **[すべてを保存]** をクリックします。  

## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、倉庫の在庫補充メッセージ スキーマを定義します。  

## <a name="next-steps"></a>次の手順  
 要求拒否メッセージのスキーマを定義します。  

## <a name="see-also"></a>参照  
 [ステップ 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)   
 [ステップ 3:要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)   
 [手順 4:マップを作成します。](../core/step-4-create-the-map.md)   
 [手順 5:EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md)   
 [BizTalk エディターを使用してスキーマを作成します。](../core/creating-schemas-using-biztalk-editor.md)   
 [BizTalk メッセージ コンテキストのプロパティについて](../core/about-biztalk-message-context-properties.md)
