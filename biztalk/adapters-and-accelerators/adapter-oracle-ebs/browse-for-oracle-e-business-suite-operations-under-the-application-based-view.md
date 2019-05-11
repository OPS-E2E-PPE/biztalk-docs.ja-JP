---
title: アプリケーション ベースのビューでの Oracle E-business Suite 操作の参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb207869-1a19-4e19-ba47-c78d2a29b36d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51abb0e1351d63baa86ccc5d2443064e557d5cba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375779"
---
# <a name="browse-for-oracle-e-business-suite-operations-under-the-application-based-view"></a>アプリケーション ベースのビューでの Oracle E-business Suite 操作の参照します。
使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Oracle E-business Suite で実行できる操作を送信および受信を参照するを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 このトピックでは、アプリケーション ベースのビューでの送信および受信操作を参照する方法について説明します。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 対象の操作のメタデータを参照するには、Oracle E-business Suite に接続する必要があります。 使用する時に、データベース、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)します。  
  
## <a name="browsing-for-outbound-operations"></a>送信操作の参照  
 アプリケーション ベースのビューでの送信操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-outbound-operations-under-the-application-based-view"></a>アプリケーション ベースのビューでの送信操作のメタデータを参照するには  
  
1. Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2. **選択コントラクト型**一覧で、選択**クライアント (送信操作)** します。  
  
3. **カテゴリを選択**ボックスは、Oracle E-business Suite の成果物を分類する別のビューを一覧表示されます。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 ルート ノード (/) が選択されているし、ルート ノードの下で利用できる一般カテゴリ ノードが記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![操作と、ルート レベルでカテゴリ](../../adapters-and-accelerators/adapter-oracle-ebs/media/559a6652-2d9d-4ecd-a1bb-4f63750c9518.gif "559a6652-2d9d-4ecd-a1bb-4f63750c9518")  
  
   > [!NOTE]
   >  ExecuteReader、ExecuteScalar、ExecuteNonQuery などの標準的な操作は、ルート レベルで使用できます。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)します。 使用してこれらの操作を実行する方法については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[ExecuteReader、executescalar、ExecuteNonQuery 操作では、BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)します。  
  
4. 展開、**アプリケーション ベースのビュー**ノードに接続されているサーバーですべて提供されている Oracle E-business suite アプリケーションを表示します。 インターフェイス テーブル、インターフェイス ビュー、同時実行プログラムは、カテゴリを表示するアプリケーションを展開し、そのアプリケーションの使用可能なセットを要求します。  
  
   > [!TIP]
   >  ツリー ビューでのフォーカスがある状態で成果物の名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、**アラート**ノードにフォーカスを保持、**アプリケーション ベースのビュー**ノード、および入力し、 `Alert`。  
  
5. 展開、**インターフェイス テーブル**Oracle アプリケーションのインターフェイス テーブルを表示するノード。 インターフェイス テーブル内のテーブルの使用可能な操作の一覧を表示する をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle のインターフェイス テーブルの参照&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/fcfbe41c-14e0-43b5-aada-c4c686aecff4.gif "fcfbe41c-14e0-43b5-aada-c4c686aecff4")  
  
   > [!NOTE]
   >  インターフェイス テーブルに BLOB の型の列が含まれている場合か、CLOB、NCLOB、BFILE アダプターも公開しますこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName\>します。 たとえば、インターフェイス テーブル FILE_DATA、BLOB、型の列がある場合、アダプターが公開、 **Read_FILE_DATA**操作。 インターフェイス テーブルに BLOB の種類の 1 つ以上の列がある場合は、CLOB、NCLOB、BFILE、アダプターは Read_ 数が同数公開\<LOBColName\>操作。  
   >   
   >  同様に、インターフェイス テーブルに BLOB の型の列が含まれている場合 CLOB、NCLOB、アダプターも公開、特定の操作をこのような列にデータを更新します。 このような操作の名前は Update_\<LOBColName\>します。 たとえば、インターフェイス テーブル FILE_DATA、BLOB、型の列がある場合、アダプターが公開、 **Update_FILE_DATA**操作。 インターフェイス テーブルに BLOB の種類の 1 つ以上の列がある場合、CLOB、NCLOB、アダプターは Update_ 数が同数公開\<LOBColName\>操作。 BFILE の型の列には、更新操作がサポートされていないことに注意してください。  
  
6. 展開、**インターフェイス ビュー** Oracle アプリケーションのインターフェイス ビューを表示するノード。 ビューで、使用可能な操作の一覧を表示する、インターフェイスの表示 をクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle のインターフェイス ビューの参照&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b.gif "f1dc14cc-ad77-47ed-b0b0-b5fc78ed545b")  
  
   > [!NOTE]
   >  場合は、インターフェイス ビューには、BLOB 型の列が含まれています、CLOB、NCLOB、BFILE、アダプターも公開しますこのような列からデータを読み取る、特定の操作。 このような操作の名前は Read_\<LOBColName\>します。 たとえば、インターフェイス ビューで、BLOB の種類の FILE_CONTENT、列がある場合、アダプターが公開、 **Read_FILE_CONTENT**操作。 CLOB、NCLOB、BFILE、アダプターが Read_ の多くの数を公開、インターフェイス ビューに BLOB の種類の 1 つ以上の列がある場合は、\<LOBColName\>操作。 注その Update_\<LOBColName\>ビューに対する操作はサポートされていません。  
  
7. をクリックして、**同時実行プログラム**内アプリケーションの同時実行プログラムを表示するノード、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle アプリケーションの同時実行プログラムを参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/71173055-4250-4406-838b-c5e9d6bf9e8c.gif "71173055-4250-4406-838b-c5e9d6bf9e8c")  
  
    この図では、Oracle アプリケーションに固有の同時実行プログラムおよびすべての Oracle アプリケーションの標準的な同時実行プログラムを示します。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 同時実行プログラムのフレンドリ名が表示されます。 ただし、同時実行プログラムのメタデータは、同時実行プログラムの実際の名前です。 たとえば、売上債権アプリケーションには、「顧客インターフェイス」同時実行プログラムが含まれています。 ただし、メタデータは、RACUST、同時実行プログラムの実際の名前を指定すると、同時実行プログラム名になります。  
  
8. をクリックして、**要求設定**内のアプリケーションの要求を表示するノードを設定、**利用可能なカテゴリと操作**ボックス。  
  
    ![Oracle アプリケーションの要求セットの参照](../../adapters-and-accelerators/adapter-oracle-ebs/media/0934f6f5-0d7a-4dad-a550-e7a4f524551b.gif "0934f6f5-0d7a-4dad-a550-e7a4f524551b")  
  
   > [!IMPORTANT]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] (または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]) 要求セットのフレンドリ名が表示されます。 ただし、要求セットのメタデータは、要求セットの実際の名前です。 たとえば、アプリケーションの DBA アプリケーションには、"DownloadPatches"要求のセットが含まれています。 ただし、メタデータが要求セットの名前、FNDRSSUB1623 として要求セットの実際の名前です。  
  
## <a name="browsing-for-inbound-operations"></a>受信操作の参照  
 アプリケーション ベースのビューでの受信操作を参照する次の手順を実行します。  
  
#### <a name="to-browse-metadata-for-inbound-operations-under-the-application-based-view"></a>アプリケーション ベースのビューでの受信操作のメタデータを参照するには  
  
1. Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2. **コントラクト型を選択します**受信操作を選択するを一覧表示**サービス (受信操作)** します。  
  
3. **カテゴリを選択**ボックスは、Oracle E-business Suite の成果物を分類する別のビューを一覧表示されます。  
  
    次に示します、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 ルート ノード (/) が選択されているし、ルート ノードの下で利用できる一般カテゴリ ノードが記載されて、**利用可能なカテゴリと操作**ボックス。  
  
    ![ルート レベルでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/9f9f95f3-c6cc-415c-b534-d5f1ad1963d5.gif "9f9f95f3-c6cc-415c-b534-d5f1ad1963d5")  
  
    受信の操作では、**通知**は、ルート レベルでも。  
  
4. 展開、**アプリケーション ベースのビュー**ノードに接続されているサーバーですべて提供されている Oracle E-business suite アプリケーションを表示します。 インターフェイス テーブルとインターフェイス ビューのカテゴリを表示するアプリケーションを展開します。  
  
   > [!TIP]
   >  ツリー ビューでのフォーカスがある状態で成果物の名前を入力してツリーで、「直近」のカテゴリ ノードを subcategory に直接進んで、**カテゴリを選択**ボックス。 たとえばに移動するため、**アラート**ノードにフォーカスを保持、**アプリケーション ベースのビュー**ノード、および入力し、 `Alert`。  
  
5. インターフェイス テーブルとそのアプリケーションの使用可能なインターフェイス ビューのカテゴリを表示する Oracle アプリケーションを展開します。 展開、**インターフェイス テーブル**と**インターフェイス ビュー**インターフェイス テーブルと、Oracle アプリケーションのインターフェイス ビューを表示するノード。 インターフェイス テーブル、またはインターフェイス ビュー テーブルの入力方向の操作を参照してください。 または、ビューをクリックして、**利用可能なカテゴリと操作**ボックス。  
  
    次の図に、インターフェイス ビューが選択されて、**カテゴリを選択**ボックスと、ビューではサポートされて受信操作が記載、**利用可能なカテゴリと操作**ボックス。  
  
    ![インターフェイス ビューでの受信操作](../../adapters-and-accelerators/adapter-oracle-ebs/media/937f46f2-d142-413f-8744-2180c7116fd4.gif "937f46f2-d142-413f-8744-2180c7116fd4")  
  
   > [!NOTE]
   >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]しない同時実行プログラムを画面し、受信操作のセットを要求しません。  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)