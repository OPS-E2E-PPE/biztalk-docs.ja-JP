---
title: "アプリケーションに基づくビューの Oracle E-business Suite 操作を参照 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb207869-1a19-4e19-ba47-c78d2a29b36d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d06cf551d033614cb75456845e059c6ec4ec8fa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-application-based-view"></a>アプリケーションに基づくビューの Oracle E-business Suite 操作の参照します。
使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Oracle E-business Suite で実行できる送受信の操作を参照するを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 このトピックでは、アプリケーション ベースのビューでの送信および受信操作を参照する方法について説明します。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]と[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 次の操作を指定のメタデータを参照する前に、Oracle E-business Suite に接続する必要があります。 データベースを使用するときに、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。  
  
## <a name="browsing-for-outbound-operations"></a>送信操作の参照  
 アプリケーション ベースのビュー アウト バウンドの操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-application-based-view"></a>アプリケーションに基づくビューの 送信操作のメタデータを参照するには  
  
1.  Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**一覧で、選択**クライアント (送信操作)**です。  
  
3.  **カテゴリを選択**ボックスには、Oracle E-business Suite の成果物を分類するさまざまなビューが一覧表示されます。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 ルート ノード (/) が選択されているし、ルート ノードで使用可能な一般カテゴリのノードで表示されます、**利用可能なカテゴリと操作**ボックス。  
  
     ![操作と、ルート レベルでカテゴリ](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
    > [!NOTE]
    >  ExecuteReader、ExecuteScalar、ExecuteNonQuery などの標準的な操作は、ルート レベルのとおりです。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。 使用してこれらの操作を実行する方法の詳細について、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[ExecuteReader、ExecuteScalar、または BizTalk Server を使用して SQL の ExecuteNonQuery Operations](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)です。  
  
4.  展開して、**アプリケーション ベースのビュー**ノードに接続されているサーバー上のすべての Oracle E-business suite 使用可能なアプリケーションを表示します。 インターフェイス テーブル、ビューのインターフェイス、同時実行のプログラム、カテゴリを表示するアプリケーションを展開し、そのアプリケーションの使用可能なセットを要求します。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、アイテムの名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、**アラート** ノードにフォーカスを保持、**アプリケーション ベースのビュー**ノード、および入力`Alert`です。  
  
5.  展開して、**インターフェイス テーブル**Oracle アプリケーション用のインターフェイス テーブルを表示するノードです。 インターフェイス テーブル内のテーブルの使用可能な操作の一覧を表示する をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle E &#45; でのインターフェイス テーブルを参照します。Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/fcfbe41c-14e0-43b5-aada-c4c686aecff4.gif "fcfbe41c-14e0-43b5-aada-c4c686aecff4")  
  
    > [!NOTE]
    >  インターフェイス テーブルには、BLOB 型の列が含まれている場合、か、CLOB、NCLOB、BFILE、アダプターまたこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName >。 たとえば、インターフェイス テーブルに列、FILE_DATA、BLOB の種類の場合、アダプターを公開、 **Read_FILE_DATA**操作します。 インターフェイス テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が数だけ公開\<LOBColName > 操作します。  
    >   
    >  同様に、インターフェイス テーブルに BLOB 型の列が含まれている場合、CLOB または NCLOB アダプターも公開、特定の操作をこのような列にデータを更新します。 このような操作の名前は Update_\<LOBColName >。 たとえば、インターフェイス テーブルに列、FILE_DATA、BLOB の種類の場合、アダプターを公開、 **Update_FILE_DATA**操作します。 Update_ 数が多く、CLOB、NCLOB、アダプターを公開インターフェイス テーブルに BLOB の種類の 1 つ以上の列がある場合は、\<LOBColName > 操作します。 BFILE 型の列には、更新操作がサポートされていないことに注意してください。  
  
6.  展開して、**インターフェイス ビュー** Oracle アプリケーション用のインターフェイス ビューを表示するノードです。 ビューを使用できる操作の一覧を表示する、インターフェイスの表示 をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle E &#45; でのインターフェイス ビューを参照します。Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b.gif "f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b")  
  
    > [!NOTE]
    >  インターフェイス ビューには、BLOB 型の列が含まれている場合、か、CLOB、NCLOB、BFILE、アダプターまたこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName >。 たとえば、インターフェイス ビューには、列、FILE_CONTENT、BLOB の種類の場合、アダプターを公開、 **Read_FILE_CONTENT**操作します。 インターフェイス ビューでは、BLOB の種類の 1 つ以上の列を含む、CLOB、NCLOB、BFILE、アダプターは公開 Read_ 数が多く\<LOBColName > 操作します。 注その Update_\<LOBColName > ビューの操作はサポートされていません。  
  
7.  クリックして、**同時実行プログラム**中のアプリケーションの同時実行プログラムを表示するノード、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle アプリケーションの同時実行プログラムを参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/71173055-4250-4406-838b-c5e9d6bf9e8c.gif "71173055-4250-4406-838b-c5e9d6bf9e8c")  
  
     この図では、Oracle アプリケーションに固有の同時実行プログラムおよび Oracle のすべてのアプリケーションの標準的な同時実行プログラムを示します。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 同時実行プログラムのフレンドリ名が表示されます。 ただし、同時実行プログラムのメタデータには、同時実行プログラムの実際の名前があります。 たとえば、売掛金アプリケーションには、「顧客インターフェイス」同時実行プログラムが含まれています。 ただし、メタデータは、同時実行プログラムの実際の名前をある RACUST と同時実行プログラム名を持ちます。  
  
8.  をクリックして、**要求設定**中のアプリケーションの要求を表示するノードの設定、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle アプリケーションの要求セットの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/0934f6f5-0d7a-4dad-a550-e7a4f524551b.gif "0934f6f5-0d7a-4dad-a550-e7a4f524551b")  
  
    > [!IMPORTANT]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 要求セットのフレンドリ名が表示されます。 ただし、要求セットのメタデータには、要求セットの実際の名前があります。 たとえば、DBA はアプリケーションのアプリケーションには、"DownloadPatches"要求のセットが含まれています。 ただし、メタデータ要求セットと名前が付け FNDRSSUB1623、要求セットの実際の名前であります。  
  
## <a name="browsing-for-inbound-operations"></a>受信操作の参照  
 アプリケーションに基づくビューの 受信の操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-application-based-view"></a>アプリケーション ベースのビューの下の受信操作のメタデータを参照するには  
  
1.  Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**を一覧表示、受信操作を選択**サービス (入力方向の操作)**です。  
  
3.  **カテゴリを選択**ボックスには、Oracle E-business Suite の成果物を分類するさまざまなビューが一覧表示されます。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 ルート ノード (/) が選択されているし、ルート ノードで使用可能な一般カテゴリのノードで表示されます、**利用可能なカテゴリと操作**ボックス。  
  
     ![ルート レベルでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
     入力方向の操作では、**通知**、ルート レベルでは使用可能なもします。  
  
4.  展開して、**アプリケーション ベースのビュー**ノードに接続されているサーバー上のすべての Oracle E-business suite 使用可能なアプリケーションを表示します。 インターフェイスのテーブルとのインターフェイス ビューのカテゴリを表示するアプリケーションを展開します。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、アイテムの名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、**アラート** ノードにフォーカスを保持、**アプリケーション ベースのビュー**ノード、および入力`Alert`です。  
  
5.  インターフェイスのテーブルとそのアプリケーションに使用できるインターフェイス ビューのカテゴリを表示する Oracle アプリケーションを展開します。 展開して、**インターフェイス テーブル**と**インターフェイス ビュー**インターフェイス テーブルと、Oracle アプリケーション用のインターフェイス ビューを表示するノードです。 テーブルの入力方向の操作を参照してください。 または、表示のインターフェイス テーブルまたはインターフェイス ビュー をクリック、**利用可能なカテゴリと操作**ボックス。  
  
     次の図に、インターフェイス ビューが選択されている、**カテゴリを選択**ボックスと、ビューではサポートされて受信操作が記載、**利用可能なカテゴリと操作**ボックス。  
  
     ![インターフェイス ビューでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]できない同時実行プログラムを提示して受信操作のセットを要求します。  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)