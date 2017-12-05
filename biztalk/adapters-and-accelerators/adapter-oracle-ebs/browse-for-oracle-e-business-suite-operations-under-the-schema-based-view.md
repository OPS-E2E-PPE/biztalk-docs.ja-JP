---
title: "スキーマに基づくビューの Oracle E-business Suite 操作を参照 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d004a99f-0db1-4cdb-80cd-ea71de4e1098
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9dedc20103787f449cc8c5ac475ef2ed2e0f82
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-schema-based-view"></a>スキーマに基づくビューの Oracle E-business Suite 操作の参照します。
使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Oracle E-business Suite で実行できる送受信の操作を参照するを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 このトピックでは、スキーマに基づくビューの下の送信および受信操作を参照する方法について説明します。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]と[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 次の操作を指定のメタデータを参照する前に、Oracle E-business Suite に接続する必要があります。 データベースを使用するときに、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。  
  
## <a name="browsing-for-outbound-operations"></a>送信操作の参照  
 スキーマに基づくビューの 送信操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-schema-based-view"></a>スキーマに基づくビューの 送信操作のメタデータを参照するには  
  
1.  Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**を一覧表示、送信操作を選択**クライアント (送信操作)**です。  
  
3.  **カテゴリを選択**ボックスには、Oracle E-business Suite の成果物を分類するさまざまなビューが一覧表示されます。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 ルート ノード (/) が選択されているし、ルート ノードで使用可能な一般カテゴリのノードで表示されます、**利用可能なカテゴリと操作**ボックス。  
  
     ![操作と、ルート レベルでカテゴリ](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
    > [!NOTE]
    >  ExecuteReader、ExecuteScalar、ExecuteNonQuery などの標準的な操作は、ルート レベルのとおりです。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。 使用してこれらの操作を実行する方法の詳細について、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[ExecuteReader、ExecuteScalar、または BizTalk Server を使用して SQL の ExecuteNonQuery Operations](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)です。  
  
4.  展開、**ビューのスキーマに基づく**ノードを基になるデータベースで定義されているスキーマを表示します。 各スキーマは、PL-SQL Api、プロシージャ、関数、テーブル、およびビューが含まれているに基づいてさらに分類されます。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、成果物の名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、 **SCOTT**スキーマにフォーカスを保持、**ビューのスキーマに基づく**ノード、および入力`SCOTT`です。  
  
5.  展開して、 **PL-SQL Api**ノードを特定のスキーマの Oracle データベースで定義されているパッケージの一覧を表示します。 関数とでは、そのパッケージ内で定義されている手順を参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのパッケージの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/582a9bd7-beed-4b36-b465-f5c4ceb6e740.gif "582a9bd7-beed-4b36-b465-f5c4ceb6e740")  
  
6.  クリックして、**プロシージャ**ノード内のプロシージャの一覧を表示する、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/7213154e-6a26-4fc3-b4ec-1658779f77d3.gif "7213154e-6a26-4fc3-b4ec-1658779f77d3")  
  
7.  クリックして、**関数**ノード内の関数の一覧を表示する、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースで関数の参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/5df9b42c-9d8b-4c81-a0ae-ba5336445837.gif "5df9b42c-9d8b-4c81-a0ae-ba5336445837")  
  
8.  展開して、**テーブル**ノードを特定のスキーマのテーブルの一覧を表示します。 内のテーブルでサポートされる操作を表示するテーブル名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースのテーブルで参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/94dd4642-1178-4d88-986b-f0ad409c414c.gif "94dd4642-1178-4d88-986b-f0ad409c414c")  
  
    > [!NOTE]
    >  場合は、テーブルには、BLOB 型の列が含まれています、CLOB、NCLOB、BFILE、アダプターも公開このような列からデータを読み取る、特定の操作します。 このような操作の名前は Read_\<LOBColName\>です。 たとえば、テーブルに列、写真、BLOB の種類の場合、アダプターを公開、 **Read_PHOTO**操作します。 テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が数だけ公開\<LOBColName\>操作します。  
    >   
    >  同様に、テーブルに BLOB 型の列が含まれている場合、CLOB または NCLOB アダプターも公開データを更新するには、このような列の特定の操作します。 このような操作の名前は Update_\<LOBColName\>です。 たとえば、テーブルに列、写真、BLOB の種類の場合、アダプターを公開、 **Update_PHOTO**操作します。 テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、アダプターは Update_ 数が多く公開\<LOBColName\>操作します。 BFILE 型の列には、更新操作がサポートされていないことに注意してください。  
  
9. 展開して、**ビュー**ノードを特定のスキーマのビューの一覧を表示します。 ビューでサポートされる操作を表示する表示名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/e1893e48-065c-4642-b076-192758d103db.gif "e1893e48-065c-4642-b076-192758d103db")  
  
    > [!NOTE]
    >  場合は、ビューには、BLOB 型の列が含まれています、CLOB、NCLOB、BFILE、アダプターも公開このような列からデータを読み取る、特定の操作します。 このような操作の名前は Read_\<LOBColName\>です。 たとえば、ビューには、列、ルール、BLOB の種類の場合、アダプターを公開、 **Read_RULE**操作します。 ビューに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が多く公開\<LOBColName\>操作します。 注その Update_\<LOBColName\>ビューの操作はサポートされていません。  
  
## <a name="browsing-for-inbound-operations"></a>受信操作の参照  
 スキーマに基づくビューの 受信の操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-schema-based-view"></a>スキーマに基づくビューの下の受信操作のメタデータを参照するには  
  
1.  Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**を一覧表示、受信操作を選択**サービス (入力方向の操作)**です。  
  
3.  **カテゴリを選択**ボックスには、Oracle E-business Suite の成果物を分類するさまざまなビューが一覧表示されます。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 ルート ノード (/) が選択されているし、ルート ノードで使用可能な一般カテゴリのノードで表示されます、**利用可能なカテゴリと操作**ボックス。  
  
     ![ルート レベルでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
     入力方向の操作では、**通知**、ルート レベルでは使用可能なもします。  
  
4.  展開、**ビューのスキーマに基づく**ノードを基になるデータベースで定義されているスキーマを表示します。 各スキーマは、PL-SQL Api、プロシージャ、関数、テーブル、およびビューが含まれているに基づいてさらに分類されます。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、成果物の名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、 **SCOTT**スキーマにフォーカスを保持、**ビューのスキーマに基づく**ノード、および入力`SCOTT`です。  
  
5.  展開して、 **PL-SQL Api**ノードを特定のスキーマの Oracle データベースで定義されているパッケージの一覧を表示します。 関数とでは、そのパッケージ内で定義されている手順を参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数およびプロシージャのそれぞれに使用できます。  
  
     ![Oracle データベースでのポーリングのパッケージの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/ab45e4a3-1425-4b23-afc2-8aecef546802.gif "ab45e4a3-1425-4b23-afc2-8aecef546802")  
  
6.  クリックして、**プロシージャ**でプロシージャの一覧を表示するノード**、利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする手順のそれぞれに使用できます。  
  
     ![Oracle データベースでのポーリングのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/04538693-5abf-4162-82e9-4107b4088b56.gif "04538693-5abf-4162-82e9-4107b4088b56")  
  
7.  クリックして、**関数**ノード内の関数の一覧を表示する、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数の各使用できます。  
  
     ![Oracle データベースでのポーリング関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/b3f4ea5b-d03f-4cb5-82b4-8fbf0a8af24b.gif "b3f4ea5b-d03f-4cb5-82b4-8fbf0a8af24b")  
  
8.  展開して、**テーブル**ノードを特定のスキーマのテーブルの一覧を表示します。 表示するテーブル名をクリックして、**ポーリング**内のテーブルに対してサポートされている操作の受信、**利用可能なカテゴリと操作**ボックス。  
  
     ![ポーリングに使用できる Oracle データベース テーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/58e9315d-3194-4a01-a505-bd1514e9d7e3.gif "58e9315d-3194-4a01-a505-bd1514e9d7e3")  
  
9. 展開して、**ビュー**ノードを特定のスキーマのビューの一覧を表示します。 表示する表示名をクリックして、**ポーリング**の受信操作で、ビューではサポートされて、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのポーリング ビュー参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1282f17-efbe-43e6-90fa-5676e04051e8.gif "f1282f17-efbe-43e6-90fa-5676e04051e8")  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)