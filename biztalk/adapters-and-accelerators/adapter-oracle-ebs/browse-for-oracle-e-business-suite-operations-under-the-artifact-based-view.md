---
title: 成果物に基づいたビュー Oracle E-business Suite 操作を参照 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 962ac1cc-826c-46d6-848a-4cd371804596
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 982f54878dc290871d7c82c4ebf124ec1f4ab903
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966808"
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-artifact-based-view"></a>成果物に基づいたビュー Oracle E-business Suite 操作の参照します。
使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Oracle E-business Suite で実行できる送受信の操作を参照するを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 このトピックでは、成果物に基づくビューの 送信および受信操作を参照する方法について説明します。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]と[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 次の操作を指定のメタデータを参照する前に、Oracle E-business Suite に接続する必要があります。 データベースを使用するときに、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。  
  
## <a name="browsing-for-outbound-operations"></a>送信操作の参照  
 成果物に基づいたビュー アウト バウンドの操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-artifact-based-view"></a>成果物に基づいたビューでの送信操作のメタデータを参照するには  
  
1.  Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**を一覧表示、送信操作を選択**クライアント (送信操作)** です。  
  
3.  **カテゴリを選択**ボックスには、Oracle E-business Suite の成果物を分類するさまざまなビューが一覧表示されます。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 ルート ノード (/) が選択されているし、ルート ノードで使用可能な一般カテゴリのノードで表示されます、**利用可能なカテゴリと操作**ボックス。  
  
     ![操作と、ルート レベルでカテゴリ](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
    > [!NOTE]
    >  ExecuteReader、ExecuteScalar、ExecuteNonQuery などの標準的な操作は、ルート レベルのとおりです。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。 使用してこれらの操作を実行する方法の詳細について、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[ExecuteReader、ExecuteScalar、または BizTalk Server を使用して SQL の ExecuteNonQuery Operations](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)です。  
  
4.  展開して、**成果物に基づいたビュー** Oracle E-business Suite と基になるデータベースの両方の成果物のカテゴリを表示するノードです。 各カテゴリがさらに分類されます (のインターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求のセットなどのアーティファクトを Oracle-E-business Suite) に属しているアプリケーションまたは (Oracle データベースなどの成果物に属しているスキーマに基づくPL-SQL Api、プロシージャ、関数、テーブル、およびビュー)。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、成果物の名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、**プロシージャ** ノードにフォーカスを保持、**成果物に基づくビュー**ノード、および入力`Procedures`です。  
  
5.  展開、**インターフェイス テーブル**ノードをすべての Oracle E-business Suite アプリケーションを表示します。 そのアプリケーションに属するすべてのインターフェイス テーブル一覧の Oracle E-business suite アプリケーションを展開します。 内のテーブルの使用可能な操作を表示するインターフェイス テーブルの名前をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    > [!NOTE]
    >  インターフェイス テーブルには、BLOB 型の列が含まれている場合、か、CLOB、NCLOB、BFILE、アダプターまたこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName\>です。 たとえば、インターフェイス テーブルに列、FILE_DATA、BLOB の種類の場合、アダプターを公開、 **Read_FILE_DATA**操作します。 インターフェイス テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が数だけ公開\<LOBColName\>操作します。  
    >   
    >  同様に、インターフェイス テーブルに BLOB 型の列が含まれている場合、CLOB または NCLOB アダプターも公開、特定の操作をこのような列にデータを更新します。 このような操作の名前は Update_\<LOBColName\>です。 たとえば、インターフェイス テーブルに列、FILE_DATA、BLOB の種類の場合、アダプターを公開、 **Update_FILE_DATA**操作します。 Update_ 数が多く、CLOB、NCLOB、アダプターを公開インターフェイス テーブルに BLOB の種類の 1 つ以上の列がある場合は、\<LOBColName\>操作します。 BFILE 型の列には、更新操作がサポートされていないことに注意してください。  
  
6.  展開して、**インターフェイス ビュー**ノードをすべての Oracle E-business Suite アプリケーションを表示します。 Oracle E-business suite アプリケーションをそのアプリケーションに属するすべてのインターフェイス ビューの一覧を展開します。 ビューで、使用できる操作を表示するインターフェイス ビュー名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    > [!NOTE]
    >  インターフェイス ビューには、BLOB 型の列が含まれている場合、か、CLOB、NCLOB、BFILE、アダプターまたこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName\>です。 たとえば、インターフェイス ビューには、列、FILE_CONTENT、BLOB の種類の場合、アダプターを公開、 **Read_FILE_CONTENT**操作します。 インターフェイス ビューでは、BLOB の種類の 1 つ以上の列を含む、CLOB、NCLOB、BFILE、アダプターは公開 Read_ 数が多く\<LOBColName\>操作します。 注その Update_\<LOBColName\>ビューの操作はサポートされていません。  
  
7.  展開して、**同時実行プログラム**ノードをすべての Oracle E-business Suite アプリケーションを表示します。 [Oracle E-business suite アプリケーションでそのアプリケーションに属するすべての同時実行プログラムを一覧表示する] をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 同時実行プログラムのフレンドリ名が表示されます。 ただし、同時実行プログラムのメタデータには、同時実行プログラムの実際の名前があります。 たとえば、売掛金アプリケーションには、「顧客インターフェイス」同時実行プログラムが含まれています。 ただし、メタデータは、同時実行プログラムの実際の名前をある RACUST と同時実行プログラム名を持ちます。  
  
8.  展開、**要求セット**ノードをすべての Oracle E-business Suite アプリケーションを表示します。 Oracle E-business suite アプリケーションでそのアプリケーションに属するすべての要求のセットを一覧表示をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 要求セットのフレンドリ名が表示されます。 ただし、要求セットのメタデータには、要求セットの実際の名前があります。 たとえば、DBA はアプリケーションのアプリケーションには、"DownloadPatches"要求のセットが含まれています。 ただし、メタデータ要求セットと名前が付け FNDRSSUB1623、要求セットの実際の名前であります。  
  
9. 展開して、 **PL-SQL Api** (使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 展開して、**現在のスキーマ (\<スキーマ名\>)** ノードをスキーマに定義されているすべてのパッケージを表示します。 関数とで、パッケージ内のプロシージャを参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのパッケージの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/7a9dc061-db0b-4a8e-bfc6-3a003ad687d8.gif "7a9dc061-db0b-4a8e-bfc6-3a003ad687d8")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義されているパッケージの一覧を表示するスキーマ ノードを展開します。 関数とで、パッケージ内のプロシージャを参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースですべてのスキーマのパッケージの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/09a4841b-b88f-490d-a49a-94e392b5493c.gif "09a4841b-b88f-490d-a49a-94e392b5493c")  
  
10. 展開して、**プロシージャ**(使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 クリックして、**現在のスキーマ (\<スキーマ名\>)** ノードをそのスキーマで定義されているすべての手順を参照して、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/6d78563a-53f7-45cc-8652-f40d4703bdf4.gif "6d78563a-53f7-45cc-8652-f40d4703bdf4")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義されたプロシージャの一覧を表示するスキーマ ノードをクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/a514d199-d6c1-44a0-bf6b-28ddf702081a.gif "a514d199-d6c1-44a0-bf6b-28ddf702081a")  
  
11. 展開して、**関数**(使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 クリックして、**現在のスキーマ (\<スキーマ名\>)** でそのスキーマに対して定義されているすべての関数を表示するノード、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマの関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/22c1cabf-9754-4ecd-be37-dbeeb7a6a8fd.gif "22c1cabf-9754-4ecd-be37-dbeeb7a6a8fd")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義された関数の一覧を表示するスキーマ ノードをクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースですべてのスキーマの関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/b4d29036-3d37-4a50-82c2-3532adbe2875.gif "b4d29036-3d37-4a50-82c2-3532adbe2875")  
  
12. 展開して、**テーブル**(使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 展開して、**現在のスキーマ (\<スキーマ名\>)** ノードをスキーマに定義されているすべてのテーブルを参照してください。 そのテーブルでサポートされる操作を表示するテーブル名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマのテーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/6ba7420f-9893-4b3e-91cb-10f29d725ad3.gif "6ba7420f-9893-4b3e-91cb-10f29d725ad3")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義されているテーブルの一覧を表示するスキーマ ノードを展開します。 そのテーブルでサポートされる操作を表示するテーブル名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベース テーブルのすべてのスキーマの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/d7c52ab4-ba27-404a-9db6-32b2a635ad2f.gif "d7c52ab4-ba27-404a-9db6-32b2a635ad2f")  
  
    > [!NOTE]
    >  場合は、テーブルには、BLOB 型の列が含まれています、CLOB、NCLOB、BFILE、アダプターも公開このような列からデータを読み取る、特定の操作します。 このような操作の名前は Read_\<LOBColName\>です。 たとえば、テーブルに列、写真、BLOB の種類の場合、アダプターを公開、 **Read_PHOTO**操作します。 テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が数だけ公開\<LOBColName\>操作します。  
    >   
    >  同様に、テーブルに BLOB 型の列が含まれている場合、CLOB または NCLOB アダプターも公開データを更新するには、このような列の特定の操作します。 このような操作の名前は Update_\<LOBColName\>です。 たとえば、テーブルに列、写真、BLOB の種類の場合、アダプターを公開、 **Update_PHOTO**操作します。 テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、アダプターは Update_ 数が多く公開\<LOBColName\>操作します。 BFILE 型の列には、更新操作がサポートされていないことに注意してください。  
  
13. 展開して、**ビュー** (使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 展開して、**現在のスキーマ (\<スキーマ名\>)** をに対して定義されているすべてのビューを表示するノードです。 そのビューでサポートされる操作を表示する表示名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースで現在のスキーマのビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a38cfed-007d-431a-af60-c9c8be5369ab.gif "2a38cfed-007d-431a-af60-c9c8be5369ab")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義されているビューの一覧を表示するスキーマ ノードを展開します。 そのビューでサポートされる操作を表示する表示名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースですべてのスキーマのビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/67ca336c-62ac-4374-87da-07cf331ea4ad.gif "67ca336c-62ac-4374-87da-07cf331ea4ad")  
  
    > [!NOTE]
    >  場合は、ビューには、BLOB 型の列が含まれています、CLOB、NCLOB、BFILE、アダプターも公開このような列からデータを読み取る、特定の操作します。 このような操作の名前は Read_\<LOBColName\>です。 たとえば、ビューには、列、ルール、BLOB の種類の場合、アダプターを公開、 **Read_RULE**操作します。 ビューに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が多く公開\<LOBColName\>操作します。 注その Update_\<LOBColName\>ビューの操作はサポートされていません。  
  
## <a name="browsing-for-inbound-operations"></a>受信操作の参照  
 成果物に基づくビューの下の受信操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-artifact-based-view"></a>成果物に基づくビューの下の受信操作のメタデータを参照するには  
  
1.  Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**を一覧表示、受信操作を選択**サービス (入力方向の操作)** です。  
  
3.  **カテゴリを選択**ボックスには、Oracle E-business Suite の成果物を分類するさまざまなビューが一覧表示されます。  
  
     次の図に示しています、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 ルート ノード (/) が選択されているし、ルート ノードで使用可能な一般カテゴリのノードで表示されます、**利用可能なカテゴリと操作**ボックス。  
  
     ![ルート レベルでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
     入力方向の操作では、**通知**、ルート レベルでは使用可能なもします。  
  
4.  展開して、**成果物に基づいたビュー** Oracle E-business Suite と基になるデータベースの両方の成果物のカテゴリを表示するノードです。 各カテゴリがさらに分類されます (のインターフェイス テーブルやインターフェイス ビューなどのアーティファクトを Oracle-E-business Suite) に属しているアプリケーションまたは (PL-SQL Api では、プロシージャ、関数などの Oracle データベースの成果物のために属しているスキーマに基づくテーブル、およびビューを使用)。  
  
    > [!TIP]
    >  ことができますに直接移動して、ツリーで、「直接」カテゴリのノードを subcategory のツリー ビューにフォーカスがあるときに、成果物の名前を入力して、**カテゴリを選択**ボックス。 例についてに移動すること、**プロシージャ** ノードにフォーカスを保持、**成果物に基づくビュー**ノード、および入力`Procedures`です。  
  
    > [!NOTE]
    >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]できない同時実行プログラムを提示して受信操作のセットを要求します。  
  
5.  インターフェイスのテーブルとそのアプリケーションに使用できるインターフェイス ビューのカテゴリを表示する Oracle アプリケーションを展開します。 展開して、**インターフェイス テーブル**と**インターフェイス ビュー**インターフェイス テーブルと、Oracle アプリケーション用のインターフェイス ビューを表示するノードです。 テーブルの入力方向の操作を参照してください。 または、表示のインターフェイス テーブルまたはインターフェイス ビュー をクリック、**利用可能なカテゴリと操作**ボックス。  
  
     次の図に、インターフェイス ビューが選択されている、**カテゴリを選択**ボックスと、ビューではサポートされて受信操作が記載、**利用可能なカテゴリと操作**ボックス。  
  
     ![インターフェイス ビューでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
6.  展開して、 **PL-SQL Api** (使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 展開して、**現在のスキーマ (\<スキーマ名\>)** ノードをスキーマに定義されているすべてのパッケージを表示します。 関数とで、パッケージ内のプロシージャを参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数およびプロシージャのそれぞれに使用できます。  
  
     ![PL &#45; を参照します。ポーリングに使用できるデータベースの Oracle の SQL Api](../../adapters-and-accelerators/adapter-oracle-ebs/media/4b31ea85-9c5a-42b4-82b2-2cb6d3ead35a.gif "4b31ea85-9c5a-42b4-82b2-2cb6d3ead35a")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義されているパッケージの一覧を表示するスキーマ ノードを展開します。 関数とで、パッケージ内のプロシージャを参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数およびプロシージャのそれぞれに使用できます。  
  
     ![PL &#45; を参照します。すべてのスキーマのポーリング SQL Api](../../adapters-and-accelerators/adapter-oracle-ebs/media/e28a803e-fcfb-4021-9225-924d54a484c0.gif "e28a803e-fcfb-4021-9225-924d54a484c0")  
  
7.  展開して、**プロシージャ**(使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 クリックして、**現在のスキーマ (\<スキーマ名\>)** ノードをそのスキーマで定義されているすべての手順を参照して、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする手順のそれぞれに使用できます。  
  
     ![プロシージャのポーリングに使用できるすべてのスキーマの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/5e78da80-d99a-44d3-8eac-f636828f8ceb.gif "5e78da80-d99a-44d3-8eac-f636828f8ceb")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義されたプロシージャの一覧を表示するスキーマ ノードをクリックして、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする手順のそれぞれに使用できます。  
  
     ![Oracle データベースでのポーリングのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/22d8e866-ed19-49f4-a6eb-683343b16cf5.gif "22d8e866-ed19-49f4-a6eb-683343b16cf5")  
  
8.  展開して、**関数**(使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 クリックして、**現在のスキーマ (\<スキーマ名\>)** でそのスキーマに対して定義されているすべての関数を表示するノード、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数の各使用できます。  
  
     ![Oracle データベースでのポーリング関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/64c0a30d-a2d6-4dee-90cb-a7e7e2bf62cf.gif "64c0a30d-a2d6-4dee-90cb-a7e7e2bf62cf")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義された関数の一覧を表示するスキーマ ノードをクリックして、**利用可能なカテゴリと操作**ボックス。  Oracle データベースをポーリングする上記の関数の各使用できます。  
  
     ![Oracle データベースでのポーリング関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/1d22c3c8-8c24-4905-8144-bdb4840244f1.gif "1d22c3c8-8c24-4905-8144-bdb4840244f1")  
  
9. 展開して、**テーブル**(使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 展開して、**現在のスキーマ (\<スキーマ名\>)** ノードをスキーマに定義されているすべてのテーブルを参照してください。 表示するテーブル名をクリックして、**ポーリング**受信操作では、そのテーブルでサポートされていません、**利用可能なカテゴリと操作**ボックス。  
  
     ![ポーリングに使用できる Oracle データベース テーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/7c60dfbf-3836-4e72-abe8-5f32a0936807.gif "7c60dfbf-3836-4e72-abe8-5f32a0936807")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義されているテーブルの一覧を表示するスキーマ ノードを展開します。 表示するテーブル名をクリックして、**ポーリング**受信操作では、そのテーブルでサポートされていません、**利用可能なカテゴリと操作**ボックス。  
  
     ![ポーリングに使用できる Oracle データベース テーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/c5fbaf59-2e79-4141-8a85-1e1b8eedcea7.gif "c5fbaf59-2e79-4141-8a85-1e1b8eedcea7")  
  
10. 展開して、**ビュー** (使用するログイン) 現在のユーザーのスキーマと基になる Oracle データベースで定義されている他のすべてのスキーマのカテゴリ ノードを表示するノードです。 展開して、**現在のスキーマ (\<スキーマ名\>)** をに対して定義されているすべてのビューを表示するノードです。 表示する表示名をクリックして、**ポーリング**の受信操作では、そのビューではサポートされて、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのポーリング ビュー参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/2299de79-9f50-433d-9e71-164f6d02bd78.gif "2299de79-9f50-433d-9e71-164f6d02bd78")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されたすべてのスキーマの一覧を表示するノードです。 スキーマに定義されているビューの一覧を表示するスキーマ ノードを展開します。 表示する表示名をクリックして、**ポーリング**の受信操作では、そのビューではサポートされて、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのポーリング ビュー参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/860e6636-1ef6-42ad-a0e2-d661e632b624.gif "860e6636-1ef6-42ad-a0e2-d661e632b624")  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)