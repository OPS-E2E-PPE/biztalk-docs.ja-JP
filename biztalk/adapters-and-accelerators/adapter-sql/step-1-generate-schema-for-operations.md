---
title: '手順 1: 操作のスキーマを生成する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63218a5e-9af2-40af-9992-ac5e204d2832
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16372bd950088b89f8e7808cda751f5fc3833944
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224962"
---
# <a name="step-1-generate-schema-for-operations"></a>手順 1: 操作のスキーマを生成します。
![2 の手順 1.](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **所要時間:** 5 分  
  
 **目標:** で SQL Server データベースを使用して、実行する操作のスキーマを生成するこの手順で、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 このチュートリアルでは、次のスキーマを生成する必要があります。  
  
-   **通知**(受信操作)。  
  
-   **UPDATE_EMPLOYEE**ストアド プロシージャ (送信操作)。  
  
-   **挿入**での操作、 **Purchase_Order**テーブル (送信操作)。  
  
## <a name="prerequisites"></a>前提条件  
 このチュートリアルを続行する前に確認します。  
  
-   内の手順を完了する必要があります[Before You 開発 BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)です。  
  
-   BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-generate-schema-for-operations"></a>操作のスキーマを生成するには  
  
1.  新しい BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このチュートリアルでは、名前とプロジェクト`Employee_PurchaseOrder`です。  
  
2.  ADAPTER_SAMPLES SQL Server データベースへの接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 使用して接続する方法についての[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio を使用してアダプター サービスの使用とアドインでの SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)です。  
  
    > [!NOTE]
    >  SQL Server を使用してに接続することも、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 ただし、このチュートリアルでは使用する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
3.  スキーマを生成、**通知**操作を受信します。  
  
    1.  ADAPTER_SAMPLES データベースに接続した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から、**選択コントラクト型**一覧で、選択**サービス (入力方向の操作)** です。  
  
    2.  **カテゴリを選択**ボックスで、ルート ノードをクリックして (**/**)。  
  
    3.  **利用可能なカテゴリと操作**ボックスで、**通知** をクリック**追加**です。 **通知**操作が表示されます、**カテゴリと操作を追加**ボックス。 **[OK]** をクリックします。  
  
4.  スキーマを生成、 **UPDATE_EMPLOYEE**でストアド プロシージャと挿入操作**Purchase_Order**テーブル。  
  
    1.  手順 2 を使用して SQL サーバーで ADAPTER_SAMPLES データベースへの接続を繰り返し、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
        > [!NOTE]
        >  同時に受信および送信操作のスキーマを生成することはできません。 そのため、手順 3. をクリックした後**OK**のスキーマを生成する**通知**操作、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を閉じます。 送信操作のスキーマを生成する SQL Server データベースに再接続する必要があります。  
  
    2.  **選択コントラクト型**一覧で、選択**クライアント (送信操作)** です。  
  
    3.  **カテゴリを選択**ボックスで、クリックして、 **Strongly-Typed プロシージャ**ノード。 **利用可能なカテゴリと操作**s ボックスで、 **UPDATE_EMPLOYEE**、クリックして**追加**です。  
  
        > [!IMPORTANT]
        >  **UPDATE_EMPLOYEE**で使用可能なストアド プロシージャも、**プロシージャ**ノード。 ただしから対象のストアド プロシージャのスキーマを生成するかどうか、**プロシージャ**ノード、応答メッセージのスキーマは使用できないデザイン時に、ストアド プロシージャを実行した後、応答メッセージを受け取りました。  
        >   
        >  このチュートリアルでは、ストアド プロシージャは、挿入操作の入力スキーマの応答スキーマをマップは、 **Purchase_Order**テーブル。 そのため、必要がありますのスキーマ、 **UPDATE_EMPLOYEE**デザイン時とするストアド プロシージャから対象のストアド プロシージャを選択する必要があります、 **Strongly-Typed プロシージャ**です。 これにより、デザイン時に、ストアド プロシージャのスキーマが表示されます。  
  
    4.  **カテゴリを選択**ボックスで、展開、**テーブル** ノードのノードをクリックして**Purchase_Order**テーブル。 **利用可能なカテゴリと操作**s ボックスで、**挿入**、 をクリックして**追加**、順にクリック**OK**です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでのスキーマを生成した**通知**(受信操作)、 **UPDATE_EMPLOYEE**ストアド プロシージャ、および**挿入**での操作、 **Purchase_Order**テーブル。 スキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]次のファイルを BizTalk プロジェクトに追加します。  
  
-   SQL Server 上の操作の呼び出しに要求メッセージのスキーマが含まれる XSD ファイル。  
  
-   XML バインド ファイルを作成 Wcf-custom 送信ポートと受信ポートで使用できる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
 スキーマの生成の詳細については、次を参照してください。[参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)です。  
  
## <a name="next-steps"></a>次の手順  
 内のスキーマの BizTalk プロジェクトでメッセージを作成する[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)です。  
  
## <a name="see-also"></a>参照  
 [レッスン 1: スキーマを生成し、メッセージ作成](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)