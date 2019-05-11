---
title: Oracle E-business Suite 操作のスキーマに基づくビューでの参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d004a99f-0db1-4cdb-80cd-ea71de4e1098
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c8791b236606bee39f8035b213f2476eab2e43e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375759"
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-schema-based-view"></a>Oracle E-business Suite 操作のスキーマに基づくビューでの参照します。
使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Oracle E-business Suite で実行できる操作を送信および受信を参照するを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 このトピックでは、送信および受信の操作のスキーマに基づくビューで参照する方法について説明します。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 対象の操作のメタデータを参照するには、Oracle E-business Suite に接続する必要があります。 使用する時に、データベース、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)します。  
  
## <a name="browsing-for-outbound-operations"></a>送信操作の参照  
 スキーマ ベースのビューでの送信操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-schema-based-view"></a>送信操作のスキーマに基づくビューでのメタデータを参照するには  
  
1. Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**リスト、送信操作の選択の**クライアント (送信操作)** します。  
  
3. **カテゴリを選択**ボックスは、Oracle E-business Suite の成果物を分類する別のビューを一覧表示されます。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 ルート ノード (/) が選択されているし、ルート ノードの下で利用できる一般カテゴリ ノードが記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![操作と、ルート レベルでカテゴリ](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
   > [!NOTE]
   >  ExecuteReader、ExecuteScalar、ExecuteNonQuery などの標準的な操作は、ルート レベルで使用できます。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)します。 使用してこれらの操作を実行する方法については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[ExecuteReader、executescalar、ExecuteNonQuery 操作では、BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)します。  
  
4. 展開、**ビューのスキーマに基づく**ノードを基になるデータベースで定義されたスキーマを参照してください。 各スキーマは、PL-SQL Api、プロシージャ、関数、テーブル、およびビューが含まれているに基づいてさらに分類されます。  
  
   > [!TIP]
   >  ツリー ビューにフォーカスがあるときに、アーティファクトの名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、 **SCOTT**スキーマ、常にフォーカスを**スキーマ ベースのビュー**ノード、および入力し、 `SCOTT`。  
  
5. 展開、 **PL-SQL Api**ノードを特定のスキーマの Oracle データベースで定義されているパッケージの一覧を表示します。 関数とでは、そのパッケージ内で定義されている手順を参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースでパッケージの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/582a9bd7-beed-4b36-b465-f5c4ceb6e740.gif "582a9bd7-beed-4b36-b465-f5c4ceb6e740")  
  
6. をクリックして、**プロシージャ**でプロシージャの一覧を表示するノード、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースでプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/7213154e-6a26-4fc3-b4ec-1658779f77d3.gif "7213154e-6a26-4fc3-b4ec-1658779f77d3")  
  
7. をクリックして、**関数**ノード内の関数の一覧を表示する、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースで関数の参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/5df9b42c-9d8b-4c81-a0ae-ba5336445837.gif "5df9b42c-9d8b-4c81-a0ae-ba5336445837")  
  
8. 展開、**テーブル**ノードを特定のスキーマのテーブルの一覧を表示します。 内のテーブルでサポートされる操作を表示するテーブル名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースでテーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/94dd4642-1178-4d88-986b-f0ad409c414c.gif "94dd4642-1178-4d88-986b-f0ad409c414c")  
  
   > [!NOTE]
   >  テーブルには、BLOB 型の列が含まれる場合、CLOB、NCLOB、BFILE、アダプターも公開しますこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName\>します。 たとえば、テーブルに列、写真、BLOB の種類の場合、アダプターが公開、 **Read_PHOTO**操作。 テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が同数公開\<LOBColName\>操作。  
   >   
   >  同様に、テーブルに BLOB の型の列が含まれている場合 CLOB、NCLOB、アダプターもを公開、特定の操作をこのような列にデータを更新します。 このような操作の名前は Update_\<LOBColName\>します。 たとえば、テーブルに列、写真、BLOB の種類の場合、アダプターが公開、 **Update_PHOTO**操作。 テーブルに BLOB の種類の 1 つ以上の列がある場合、CLOB、NCLOB、アダプターは Update_ 数が同数公開\<LOBColName\>操作。 BFILE の型の列には、更新操作がサポートされていないことに注意してください。  
  
9. 展開、**ビュー**ノードを特定のスキーマのビューの一覧を表示します。 ビューでサポートされる操作を表示する表示名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/e1893e48-065c-4642-b076-192758d103db.gif "e1893e48-065c-4642-b076-192758d103db")  
  
    > [!NOTE]
    >  場合は、ビューには、BLOB 型の列が含まれています、CLOB、NCLOB、BFILE、アダプターも公開しますこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName\>します。 たとえば、ビュー列での BLOB の種類のルールがある場合、アダプターが公開、 **Read_RULE**操作。 ビューに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が同数公開\<LOBColName\>操作。 注その Update_\<LOBColName\>ビューに対する操作はサポートされていません。  
  
## <a name="browsing-for-inbound-operations"></a>受信操作の参照  
 スキーマ ベースのビューでの受信操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-schema-based-view"></a>受信操作のスキーマに基づくビューでのメタデータを参照するには  
  
1. Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**受信操作を選択するを一覧表示**サービス (受信操作)** します。  
  
3. **カテゴリを選択**ボックスは、Oracle E-business Suite の成果物を分類する別のビューを一覧表示されます。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 ルート ノード (/) が選択されているし、ルート ノードの下で利用できる一般カテゴリ ノードが記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![ルート レベルでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
    受信の操作では、**通知**は、ルート レベルでも。  
  
4. 展開、**ビューのスキーマに基づく**ノードを基になるデータベースで定義されたスキーマを参照してください。 各スキーマは、PL-SQL Api、プロシージャ、関数、テーブル、およびビューが含まれているに基づいてさらに分類されます。  
  
   > [!TIP]
   >  ツリー ビューにフォーカスがあるときに、アーティファクトの名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、 **SCOTT**スキーマ、常にフォーカスを**スキーマ ベースのビュー**ノード、および入力し、 `SCOTT`。  
  
5. 展開、 **PL-SQL Api**ノードを特定のスキーマの Oracle データベースで定義されているパッケージの一覧を表示します。 関数とでは、そのパッケージ内で定義されている手順を参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数およびプロシージャのそれぞれに使用できます。  
  
    ![Oracle データベースでのポーリングのパッケージの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/ab45e4a3-1425-4b23-afc2-8aecef546802.gif "ab45e4a3-1425-4b23-afc2-8aecef546802")  
  
6. をクリックして、**プロシージャ**でプロシージャの一覧を表示するノード **、利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする手順のそれぞれに使用できます。  
  
    ![Oracle データベースでのポーリングのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/04538693-5abf-4162-82e9-4107b4088b56.gif "04538693-5abf-4162-82e9-4107b4088b56")  
  
7. をクリックして、**関数**ノード内の関数の一覧を表示する、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数の各使用できます。  
  
    ![Oracle データベースでのポーリングの関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/b3f4ea5b-d03f-4cb5-82b4-8fbf0a8af24b.gif "b3f4ea5b-d03f-4cb5-82b4-8fbf0a8af24b")  
  
8. 展開、**テーブル**ノードを特定のスキーマのテーブルの一覧を表示します。 表示するテーブル名をクリックして、**ポーリング**内のテーブルでサポートされている操作の受信、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle データベースでのポーリングのテーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/58e9315d-3194-4a01-a505-bd1514e9d7e3.gif "58e9315d-3194-4a01-a505-bd1514e9d7e3")  
  
9. 展開、**ビュー**ノードを特定のスキーマのビューの一覧を表示します。 表示する表示名をクリックして、**ポーリング**の受信操作で、ビューではサポートされて、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのポーリングのビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1282f17-efbe-43e6-90fa-5676e04051e8.gif "f1282f17-efbe-43e6-90fa-5676e04051e8")  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)