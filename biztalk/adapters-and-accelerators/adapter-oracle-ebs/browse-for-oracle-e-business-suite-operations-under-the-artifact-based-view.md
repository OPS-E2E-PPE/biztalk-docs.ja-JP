---
title: 成果物ベースのビューでの Oracle E-business Suite 操作の参照 |Microsoft Docs
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
ms.openlocfilehash: a70b378393839a4f1f03dbd6841d85fbd06fd18d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979627"
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-artifact-based-view"></a>成果物ベースのビューでの Oracle E-business Suite 操作の参照します。
使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Oracle E-business Suite で実行できる操作を送信および受信を参照するを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 このトピックでは、成果物ベースのビューでの送信および受信操作を参照する方法について説明します。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 対象の操作のメタデータを参照するには、Oracle E-business Suite に接続する必要があります。 使用する時に、データベース、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)します。  
  
## <a name="browsing-for-outbound-operations"></a>送信操作の参照  
 成果物ベースのビューでの送信操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-artifact-based-view"></a>成果物ベースのビューでの送信操作のメタデータを参照するには  
  
1. Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**リスト、送信操作の選択の**クライアント (送信操作)** します。  
  
3. **カテゴリを選択**ボックスは、Oracle E-business Suite の成果物を分類する別のビューを一覧表示されます。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 ルート ノード (/) が選択されているし、ルート ノードの下で利用できる一般カテゴリ ノードが記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![操作と、ルート レベルでカテゴリ](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
   > [!NOTE]
   >  ExecuteReader、ExecuteScalar、ExecuteNonQuery などの標準的な操作は、ルート レベルで使用できます。 これらの操作の詳細については、[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)を参照してください。 使用してこれらの操作を実行する方法については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[ExecuteReader、executescalar、ExecuteNonQuery 操作では、BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)します。  
  
4. 展開、**成果物ベースのビュー**成果物を Oracle E-business Suite と基になるデータベースの両方のカテゴリを表示するノード。 各カテゴリが (のインターフェイス テーブル、インターフェイス ビュー、同時実行プログラム、および要求セットなどの Oracle-E-business Suite の成果物) に属しているアプリケーションまたは (Oracle データベースなどの成果物に属しているスキーマに基づいてさらに分類します。PL-SQL Api、プロシージャ、関数、テーブル、およびビュー)。  
  
   > [!TIP]
   >  ツリー ビューにフォーカスがあるときに、アーティファクトの名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、**プロシージャ**ノードにフォーカスを保持、**成果物ベースのビュー**ノード、および入力`Procedures`。  
  
5. 展開、**インターフェイス テーブル**Oracle E-business Suite のすべてのアプリケーションを表示するノード。 そのアプリケーションに属するすべてのインターフェイス テーブルを一覧表示、Oracle E-business suite のアプリケーションを展開します。 内のテーブルの使用可能な操作を参照してください、インターフェイス テーブル名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
   > [!NOTE]
   >  インターフェイス テーブルに BLOB の型の列が含まれている場合か、CLOB、NCLOB、BFILE アダプターも公開しますこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName\>します。 たとえば、インターフェイス テーブル FILE_DATA、BLOB、型の列がある場合、アダプターが公開、 **Read_FILE_DATA**操作。 インターフェイス テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が同数公開\<LOBColName\>操作。  
   >   
   >  同様に、インターフェイス テーブルに BLOB の型の列が含まれている場合 CLOB、NCLOB、アダプターも公開、特定の操作をこのような列にデータを更新します。 このような操作の名前は Update_\<LOBColName\>します。 たとえば、インターフェイス テーブル FILE_DATA、BLOB、型の列がある場合、アダプターが公開、 **Update_FILE_DATA**操作。 インターフェイス テーブルに BLOB の種類の 1 つ以上の列がある場合、CLOB、NCLOB、アダプターは Update_ 数が同数公開\<LOBColName\>操作。 BFILE の型の列には、更新操作がサポートされていないことに注意してください。  
  
6. 展開、**インターフェイス ビュー** Oracle E-business Suite のすべてのアプリケーションを表示するノード。 そのアプリケーションに属するすべてのインターフェイス ビューを一覧表示、Oracle E-business suite のアプリケーションを展開します。 ビューで、使用可能な操作を参照してください、インターフェイス ビュー名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
   > [!NOTE]
   >  場合は、インターフェイス ビューには、BLOB 型の列が含まれています、CLOB、NCLOB、BFILE、アダプターも公開しますこのような列からデータを読み取る、特定の操作。 このような操作の名前は、Read_\<LOBColName\>します。 たとえば、インターフェイス ビューで、BLOB の種類の FILE_CONTENT、列がある場合、アダプターが公開、 **Read_FILE_CONTENT**操作。 CLOB、NCLOB、BFILE、アダプターが Read_ の多くの数を公開、インターフェイス ビューに BLOB の種類の 1 つ以上の列がある場合は、\<LOBColName\>操作。 注その Update_\<LOBColName\>ビューに対する操作はサポートされていません。  
  
7. 展開、**同時実行プログラム**Oracle E-business Suite のすべてのアプリケーションを表示するノード。 [Oracle E-business suite アプリケーションでそのアプリケーションに属するすべての同時実行プログラムを一覧表示する] をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 同時実行プログラムのフレンドリ名が表示されます。 ただし、同時実行プログラムのメタデータは、同時実行プログラムの実際の名前です。 たとえば、売上債権アプリケーションには、「顧客インターフェイス」同時実行プログラムが含まれています。 ただし、メタデータは、RACUST、同時実行プログラムの実際の名前を指定すると、同時実行プログラム名になります。  
  
8. 展開、**要求セット**Oracle E-business Suite のすべてのアプリケーションを表示するノード。 [Oracle E-business suite アプリケーションでそのアプリケーションに属するすべての要求セットを一覧表示] をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 要求セットのフレンドリ名が表示されます。 ただし、要求セットのメタデータは、要求セットの実際の名前です。 たとえば、アプリケーションの DBA アプリケーションには、"DownloadPatches"要求のセットが含まれています。 ただし、メタデータが要求セットの名前、FNDRSSUB1623 として要求セットの実際の名前です。  
  
9. 展開、 **PL-SQL Api** (使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 展開、**現在のスキーマ (\<スキーマ名\>)** ノードをスキーマに定義されているすべてのパッケージを参照してください。 関数と、パッケージ内のプロシージャを参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでパッケージの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/7a9dc061-db0b-4a8e-bfc6-3a003ad687d8.gif "7a9dc061-db0b-4a8e-bfc6-3a003ad687d8")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 スキーマに定義されているパッケージの一覧を表示するスキーマ ノードを展開します。 関数と、パッケージ内のプロシージャを参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースですべてのスキーマのパッケージの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/09a4841b-b88f-490d-a49a-94e392b5493c.gif "09a4841b-b88f-490d-a49a-94e392b5493c")  
  
10. 展開、**プロシージャ**(使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 をクリックして、**現在のスキーマ (\<スキーマ名\>)** ノードをそのスキーマで定義されているすべての手順を参照して、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/6d78563a-53f7-45cc-8652-f40d4703bdf4.gif "6d78563a-53f7-45cc-8652-f40d4703bdf4")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 [スキーマ ノードのスキーマに定義されたプロシージャの一覧を表示する] をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/a514d199-d6c1-44a0-bf6b-28ddf702081a.gif "a514d199-d6c1-44a0-bf6b-28ddf702081a")  
  
11. 展開、**関数**(使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 をクリックして、**現在のスキーマ (\<スキーマ名\>)** ノードでそのスキーマに対して定義されているすべての機能を**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマの関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/22c1cabf-9754-4ecd-be37-dbeeb7a6a8fd.gif "22c1cabf-9754-4ecd-be37-dbeeb7a6a8fd")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 このスキーマに定義された関数の一覧を表示するスキーマ ノードをクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマのすべての関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/b4d29036-3d37-4a50-82c2-3532adbe2875.gif "b4d29036-3d37-4a50-82c2-3532adbe2875")  
  
12. 展開、**テーブル**(使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 展開、**現在のスキーマ (\<スキーマ名\>)** ノードをスキーマに定義されているすべてのテーブルを参照してください。 そのテーブルでサポートされる操作を表示するテーブル名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでスキーマのテーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/6ba7420f-9893-4b3e-91cb-10f29d725ad3.gif "6ba7420f-9893-4b3e-91cb-10f29d725ad3")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 スキーマに定義されているテーブルの一覧を表示するスキーマ ノードを展開します。 そのテーブルでサポートされる操作を表示するテーブル名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![すべてのスキーマの Oracle データベースのテーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/d7c52ab4-ba27-404a-9db6-32b2a635ad2f.gif "d7c52ab4-ba27-404a-9db6-32b2a635ad2f")  
  
    > [!NOTE]
    >  参照、検索、および Oracle E-business Suite 操作のメタデータを取得 このような操作の名前は Read_\<LOBColName\>します。 たとえば、テーブルに列、写真、BLOB の種類の場合、アダプターが公開、 **Read_PHOTO**操作。 テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が同数公開\<LOBColName\>操作。  
    >   
    >  同様に、テーブルに BLOB の型の列が含まれている場合 CLOB、NCLOB、アダプターもを公開、特定の操作をこのような列にデータを更新します。 このような操作の名前は Update_\<LOBColName\>します。 たとえば、テーブルに列、写真、BLOB の種類の場合、アダプターが公開、 **Update_PHOTO**操作。 テーブルに BLOB の種類の 1 つ以上の列がある場合、CLOB、NCLOB、アダプターは Update_ 数が同数公開\<LOBColName\>操作。 BFILE の型の列には、更新操作がサポートされていないことに注意してください。  
  
13. 展開、**ビュー** (使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 展開、**現在のスキーマ (\<スキーマ名\>)** が定義されているすべてのビューを表示するノード。 そのビューでサポートされる操作を表示する表示名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースで現在のスキーマのビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a38cfed-007d-431a-af60-c9c8be5369ab.gif "2a38cfed-007d-431a-af60-c9c8be5369ab")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 スキーマに定義されているビューの一覧を表示するスキーマ ノードを展開します。 そのビューでサポートされる操作を表示する表示名をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースですべてのスキーマのビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/67ca336c-62ac-4374-87da-07cf331ea4ad.gif "67ca336c-62ac-4374-87da-07cf331ea4ad")  
  
    > [!NOTE]
    >  場合は、ビューには、BLOB 型の列が含まれています、CLOB、NCLOB、BFILE、アダプターも公開しますこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName\>します。 たとえば、ビュー列での BLOB の種類のルールがある場合、アダプターが公開、 **Read_RULE**操作。 ビューに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が同数公開\<LOBColName\>操作。 注その Update_\<LOBColName\>ビューに対する操作はサポートされていません。  
  
## <a name="browsing-for-inbound-operations"></a>受信操作の参照  
 成果物ベースのビューでの受信操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-artifact-based-view"></a>成果物ベースのビューでの受信操作のメタデータを参照するには  
  
1. Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**受信操作を選択するを一覧表示**サービス (受信操作)** します。  
  
3. **カテゴリを選択**ボックスは、Oracle E-business Suite の成果物を分類する別のビューを一覧表示されます。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 ルート ノード (/) が選択されているし、ルート ノードの下で利用できる一般カテゴリ ノードが記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![ルート レベルでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
    受信の操作では、**通知**は、ルート レベルでも。  
  
4. 展開、**成果物ベースのビュー**成果物を Oracle E-business Suite と基になるデータベースの両方のカテゴリを表示するノード。 各カテゴリが (のインターフェイス テーブルとインターフェイス ビューなどの Oracle-E-business Suite の成果物) に属しているアプリケーションまたは (の PL-SQL Api、プロシージャ、関数などの Oracle データベース アイテムが属するスキーマに基づいてさらに分類します。テーブル、およびビューを使用)。  
  
   > [!TIP]
   >  ツリー ビューにフォーカスがあるときに、アーティファクトの名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、**プロシージャ**ノードにフォーカスを保持、**成果物ベースのビュー**ノード、および入力`Procedures`。  
   > 
   > [!NOTE]
   >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]しない同時実行プログラムを画面し、受信操作のセットを要求しません。  
  
5. インターフェイス テーブルとそのアプリケーションの使用可能なインターフェイス ビューのカテゴリを表示する Oracle アプリケーションを展開します。 展開、**インターフェイス テーブル**と**インターフェイス ビュー**インターフェイス テーブルと、Oracle アプリケーションのインターフェイス ビューを表示するノード。 インターフェイス テーブル、またはインターフェイス ビュー テーブルの入力方向の操作を参照してください。 または、ビューをクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    次の図に、インターフェイス ビューが選択されて、**カテゴリを選択**ボックスと、ビューではサポートされて受信操作が記載、**利用可能なカテゴリと操作**ボックス。  
  
    ![インターフェイス ビューでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
6. 展開、 **PL-SQL Api** (使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 展開、**現在のスキーマ (\<スキーマ名\>)** ノードをスキーマに定義されているすべてのパッケージを参照してください。 関数と、パッケージ内のプロシージャを参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数およびプロシージャのそれぞれに使用できます。  
  
    ![参照 PL&#45;Oracle では、SQL Api のデータベースのポーリング](../../adapters-and-accelerators/adapter-oracle-ebs/media/4b31ea85-9c5a-42b4-82b2-2cb6d3ead35a.gif "4b31ea85-9c5a-42b4-82b2-2cb6d3ead35a")  
  
    同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 スキーマに定義されているパッケージの一覧を表示するスキーマ ノードを展開します。 関数と、パッケージ内のプロシージャを参照してください。 パッケージ名をクリックして、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数およびプロシージャのそれぞれに使用できます。  
  
    ![参照 PL&#45;SQL Api のすべてのスキーマのポーリング](../../adapters-and-accelerators/adapter-oracle-ebs/media/e28a803e-fcfb-4021-9225-924d54a484c0.gif "e28a803e-fcfb-4021-9225-924d54a484c0")  
  
7. 展開、**プロシージャ**(使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 をクリックして、**現在のスキーマ (\<スキーマ名\>)** ノードをそのスキーマで定義されているすべての手順を参照して、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする手順のそれぞれに使用できます。  
  
    ![すべてのスキーマのポーリングのための手順を参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/5e78da80-d99a-44d3-8eac-f636828f8ceb.gif "5e78da80-d99a-44d3-8eac-f636828f8ceb")  
  
    同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 [スキーマ ノードのスキーマに定義されたプロシージャの一覧を表示する] をクリックして、**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする手順のそれぞれに使用できます。  
  
    ![Oracle データベースでのポーリングのプロシージャの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/22d8e866-ed19-49f4-a6eb-683343b16cf5.gif "22d8e866-ed19-49f4-a6eb-683343b16cf5")  
  
8. 展開、**関数**(使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 をクリックして、**現在のスキーマ (\<スキーマ名\>)** ノードでそのスキーマに対して定義されているすべての機能を**利用可能なカテゴリと操作**ボックス。 Oracle データベースをポーリングする上記の関数の各使用できます。  
  
    ![Oracle データベースでのポーリングの関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/64c0a30d-a2d6-4dee-90cb-a7e7e2bf62cf.gif "64c0a30d-a2d6-4dee-90cb-a7e7e2bf62cf")  
  
    同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 このスキーマに定義された関数の一覧を表示するスキーマ ノードをクリックして、**利用可能なカテゴリと操作**ボックス。  Oracle データベースをポーリングする上記の関数の各使用できます。  
  
    ![Oracle データベースでのポーリングの関数参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/1d22c3c8-8c24-4905-8144-bdb4840244f1.gif "1d22c3c8-8c24-4905-8144-bdb4840244f1")  
  
9. 展開、**テーブル**(使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 展開、**現在のスキーマ (\<スキーマ名\>)** ノードをスキーマに定義されているすべてのテーブルを参照してください。 表示するテーブル名をクリックして、**ポーリング**受信操作では、そのテーブルでサポートされていません、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのポーリングのテーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/7c60dfbf-3836-4e72-abe8-5f32a0936807.gif "7c60dfbf-3836-4e72-abe8-5f32a0936807")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 スキーマに定義されているテーブルの一覧を表示するスキーマ ノードを展開します。 表示するテーブル名をクリックして、**ポーリング**受信操作では、そのテーブルでサポートされていません、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのポーリングのテーブルの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/c5fbaf59-2e79-4141-8a85-1e1b8eedcea7.gif "c5fbaf59-2e79-4141-8a85-1e1b8eedcea7")  
  
10. 展開、**ビュー** (使用するログイン) 現在のユーザー スキーマを基になる Oracle データベースで定義されている他のすべてのスキーマ カテゴリ ノードを表示するノード。 展開、**現在のスキーマ (\<スキーマ名\>)** が定義されているすべてのビューを表示するノード。 表示する表示名をクリックして、**ポーリング**の受信操作では、そのビューではサポートされて、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのポーリングのビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/2299de79-9f50-433d-9e71-164f6d02bd78.gif "2299de79-9f50-433d-9e71-164f6d02bd78")  
  
     同様に、展開、**すべてのスキーマ**Oracle データベースで定義されているすべてのスキーマの一覧を表示するノード。 スキーマに定義されているビューの一覧を表示するスキーマ ノードを展開します。 表示する表示名をクリックして、**ポーリング**の受信操作では、そのビューではサポートされて、**利用可能なカテゴリと操作**ボックス。  
  
     ![Oracle データベースでのポーリングのビューの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/860e6636-1ef6-42ad-a0e2-d661e632b624.gif "860e6636-1ef6-42ad-a0e2-d661e632b624")  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)