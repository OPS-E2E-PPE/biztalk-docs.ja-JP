---
title: '手順 1: 操作のスキーマの生成 |Microsoft Docs'
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
ms.openlocfilehash: 6eb6de636ba2ee587fa1da3720c38ef517f0ba01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997859"
---
# <a name="step-1-generate-schema-for-operations"></a>手順 1: 操作のスキーマを生成します。
![手順 2 の 1](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **所要時間:** 5 分  
  
 **目標:** 、SQL Server データベースを使用して実行する操作のスキーマを生成するこの手順で、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 このチュートリアルで、次のスキーマを生成する必要があります。  
  
-   **通知**(入力方向の操作)。  
  
-   **UPDATE_EMPLOYEE**ストアド プロシージャ (送信操作)。  
  
-   **挿入**操作、 **Purchase_Order**テーブル (送信操作)。  
  
## <a name="prerequisites"></a>前提条件  
 チュートリアルを続行する前に、ことを確認してください。  
  
-   」の手順を完了する必要があります[Before You 開発 BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)します。  
  
-   BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-generate-schema-for-operations"></a>操作のスキーマを生成するには  
  
1. 新しい BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このチュートリアルでは、名前としてプロジェクト`Employee_PurchaseOrder`します。  
  
2. ADAPTER_SAMPLES SQL Server データベースに接続する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 使用して接続する方法についての[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio を使用して Consume Adapter Service アドイン内の SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)します。  
  
   > [!NOTE]
   >  使用して SQL サーバーに接続することも、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 ただし、このチュートリアルで使用する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
3. スキーマの生成、**通知**操作を受信します。  
  
   1. ADAPTER_SAMPLES データベースに接続した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から、**コントラクト型を選択します**一覧で、選択**サービス (受信操作)** します。  
  
   2. **カテゴリを選択**ボックスに、ルート ノードをクリックします (**/**)。  
  
   3. **利用可能なカテゴリと操作**ボックスで、**通知**クリック**追加**します。 **通知**で操作が表示されます、**カテゴリと操作を追加**ボックス。 **[OK]** をクリックします。  
  
4. スキーマの生成、 **UPDATE_EMPLOYEE**でストアド プロシージャと挿入操作**Purchase_Order**テーブル。  
  
   1. 手順 2 を使用して SQL Server で ADAPTER_SAMPLES データベースへの接続を繰り返し、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
      > [!NOTE]
      >  同時に受信と送信操作のスキーマを生成することはできません。 そのため、手順 3. で、クリックした後**OK**のスキーマを生成する**通知**操作、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を閉じます。 送信操作のスキーマを生成する SQL Server データベースに再接続する必要があります。  
  
   2. **選択コントラクト型**一覧で、選択**クライアント (送信操作)** します。  
  
   3. **カテゴリを選択**ボックスで、、 **Strongly-Typed プロシージャ**ノード。 **利用可能なカテゴリと操作**s ボックスで、 **UPDATE_EMPLOYEE**、 をクリックし、**追加**します。  
  
      > [!IMPORTANT]
      >  **UPDATE_EMPLOYEE**で使用可能なストアド プロシージャも、**プロシージャ**ノード。 ただしの下にあるストアド プロシージャのスキーマを生成するかどうか、**プロシージャ**ノード、応答メッセージのスキーマがデザイン時にありませんが、ストアド プロシージャを実行した後、応答メッセージを受け取りました。  
      >   
      >  このチュートリアルで挿入操作の入力スキーマにストアド プロシージャの応答スキーマをマップ、 **Purchase_Order**テーブル。 したがってのスキーマが必要、 **UPDATE_EMPLOYEE**デザイン時とするストアド プロシージャは、の下にあるストアド プロシージャを選択する必要があります、 **Strongly-Typed プロシージャ**します。 これにより、デザイン時に、ストアド プロシージャのスキーマが表示されます。  
  
   4. **カテゴリを選択**ボックスで、展開、**テーブル**ノード、ノードをクリックして**Purchase_Order**テーブル。 **利用可能なカテゴリと操作**s ボックスで、**挿入**、 をクリックして**追加**、順にクリックします**OK**します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 このステップでのスキーマを生成した**通知**(入力方向の操作)、 **UPDATE_EMPLOYEE**ストアド プロシージャと**挿入**操作、 **Purchase_Order**テーブル。 スキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を BizTalk プロジェクトに、次のファイルを追加します。  
  
- SQL Server での操作を呼び出す要求メッセージのスキーマが含まれる XSD ファイル。  
  
- XML バインド ファイルを作成する Wcf-custom 送信ポートと受信ポートで使用できる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
  スキーマを生成する詳細については、[参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)を参照してください。  
  
## <a name="next-steps"></a>次の手順  
 内のスキーマの BizTalk プロジェクトでメッセージを作成する[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)です。  
  
## <a name="see-also"></a>参照  
 [レッスン 1: スキーマを生成してメッセージを作成する](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)