---
title: "Oracle E-business Suite 操作のメタデータを取得する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 566ae086-183a-47db-8f93-12b5903c85c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1443219f8562caee53547be3f78df15834ddf4b7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="get-the-oracle-e-business-suite-operations-metadata"></a>Oracle E-business Suite 操作のメタデータを取得します。
使用することができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Oracle E-business Suite の選択した成果物のためのスキーマを生成します。 参照して、呼び出し先のアイテムの検索し、それらの成果物のスキーマを生成し、Oracle E-business Suite へのスキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]と[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 次の操作を指定のメタデータを取得する前に、Oracle E-business Suite に接続する必要があります。 データベースを使用するときに、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in"></a>使用してスキーマを生成する、アダプターを使用する追加のサービス  
  
> [!NOTE]
>  そのカテゴリのサブツリー内のすべての操作を返すカテゴリ ノードを選択することができます: たとえば、選択することができます、**同時実行プログラム**ことも (スキーマを生成する Oracle アプリケーションの同時実行プログラムがすべて) ノード特定の同時実行プログラムを選択します。 ノードの詳細については、ノード Id でメタデータを参照してください。  
  
#### <a name="to-generate-schema-for-oracle-e-business-suite-artifacts"></a>Oracle E-business Suite の成果物のためのスキーマを生成するには  
  
1.  Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
    > [!IMPORTANT]
    >  使用して操作を実行するためのスキーマを生成する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]設定する必要があります、 **EnableBizTalkCompatibilityMode**にプロパティのバインド**True**です。 Oracle E-business Suite への接続を確立中に、このバインドのプロパティを設定する必要があります。  
  
2.  **選択コントラクト型**一覧で、受信または送信操作のスキーマを生成しているかどうかに基づいてコントラクトの型を選択します。  
  
3.  メタデータを生成するカテゴリ ノードをクリックします。 たとえば、Oracle アプリケーション内で同時実行プログラムのメタデータを生成する場合は、クリックして**同時実行プログラム**です。  
  
4.  カテゴリのノードを展開し、メタデータを生成する、そのノード内の特定の項目を選択します。 たとえば、"バンキング Center"アプリケーションの同時実行プログラムのメタデータを生成するには、次のように展開します。、**同時実行プログラム**ノードをクリックして**バンキング Center**です。  
  
5.  **利用可能なカテゴリと操作**ボックスを起動し、をクリックする操作を選択**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 たとえば、「パージ FTP 銀行アカウント」と"Get_Status"同時実行プログラムを起動する操作名をクリック**追加**です。  
  
     次の図に示しています、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、選択した操作を一覧表示します。  
  
     ![Oracle E &#45; からメタデータを取得します。Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/df7de132-9177-4de7-a620-59dbd561efe5.gif "df7de132-9177-4de7-a620-59dbd561efe5")  
  
     複数の操作のスキーマを生成する場合は、BizTalk プロジェクトのコンパイルに失敗する可能性がありますをこれらのスキーマ間で重複する要素定義である可能性があります。 たとえば、"Op1"、操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、データ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"が"CT1"のデータ型のパラメーターにはも含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているために、コンパイル エラーが表示されます。 このような場合に、次のお勧めします。  
  
    -   1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 これにより、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]複雑なデータ型"CT1"の定義は 1 つだけが生成されます。  
  
    -   複数の異なる実行で複数の操作のスキーマを生成するかどうか[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意なスキーマ型を生成** チェック ボックスを生成される XSD ファイルの一意の名前空間に含まれるように、複雑なデータは、"CT1"を入力します。  
  
6.  **[OK]**をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
    > [!NOTE]
    >  Oracle の成果物に対する操作のメタデータを生成する アダプター サービスのアドインを使用している場合は、既定でファイルが作成特定の名前付け規則に: 生成された XSD ファイル名には次の 3 つの部分。  
    >   
    >  -   提供される"OracleEBSBinding"またはプレフィックス、**ファイル名のプレフィックス**ボックス。  
    > -   含まれる名、 **fileNameHint**で生成される WSDL 注釈タグ。 操作については、ファイル名のヒントは、操作のグループと同じです。 複合型では、ファイル名のヒントは、"http://schemas.microsoft.com/OracleEBS/2008/05/"プレフィックスなしの名前空間です。 たとえば、インターフェイス テーブル操作のファイル名のヒントには、規則が次に\<InterfaceTables\>+ < app_short_name > + < interface_table_name >。  
    > -   (省略可能)ファイル名が一意であることを確認する整数。  
    >   
    >  最後に、XSD ファイルの名前は到着した時に < file_name_prefix > として +\<fileNameHint\>+ n、"n"は一意の整数。  
  
    > [!NOTE]
    >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]時に指定されたバインディングのプロパティを含むバインド ファイル (XML ファイル) も作成操作と、操作を呼び出す SOAP アクションのスキーマを生成します。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを接続 URI の WCF カスタム ポート、バインディング プロパティ、および SOAP アクションの作成を設定します。 詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。  
  
     Oracle E-business Suite の成果物のためのメタデータが正常に生成されました。 メタデータを使用すると、特定の操作を実行するのに Oracle E-business Suite にメッセージを送信します。 参照してください[Oracle E-business Suite アダプターを使用して BizTalk の開発アプリケーション](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)これらの操作を実行する方法に関する詳細についてはします。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>WCF クライアントまたは WCF サービス コントラクトを使用して、生成する、プラグイン アダプター サービス参照の追加  
 使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]いずれかの送信操作用の WCF クライアント コードまたは受信操作のための WCF サービス コードを生成します。  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-oracle-e-business-suite-operations"></a>Oracle E-business Suite 操作のための WCF クライアント クラスまたはサービス コントラクトを生成するには  
  
1.  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**選択コントラクト型**ドロップダウン リストで、基にするかどうかを実行する受信または送信操作コントラクトの型を選択します。  
  
2.  参照または WCF クライアント (または WCF サービス コントラクト) を生成する特定の操作またはインターフェイス テーブルの場合) などのカテゴリを検索します。   
    例については、AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルでの操作の参照、**カテゴリを選択**ボックス。  
  
    1.  ルート ノードを展開 (**/**) を for Oracle E-business Suite 操作が表示されるカテゴリを表示します。 同じインターフェイス テーブルは 使用できる、**アプリケーション ベースのビュー**ノードだけでなく**成果物に基づいたビュー**ノード。 この例では、クラスを生成する、WCF クライアントから、**アプリケーション ベースのビュー**ノード。  
  
    2.  [ルート] ノードで、展開、**アプリケーション ベースのビュー** Oracle E-business Suite で利用可能なアプリケーションを表示するノードです。  
  
    3.  ノードを展開、**債権**アプリケーションの順に展開し、**インターフェイス テーブル**ノード。  
  
    4.  をクリックして、 **AR_ARCHIVE_PURGE_INTERIM**インターフェイス テーブルのノード、および、**利用可能なカテゴリと操作**ボックスで、WCF クライアント (または WCF サービスを生成する操作を選択コントラクト) をクリックして**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
         次の図に示しています、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] Insert と Select 操作と AR_ARCHIVE_PURGE_INTERIM テーブルを選択します。  
  
         ![WCF クライアントまたはサービス コントラクトの生成](../../adapters-and-accelerators/adapter-oracle-ebs/media/oraebs-adap-add-adap-serv-refs.gif "oraebs_adap_add_adap_serv_refs")  
  
        > [!IMPORTANT]
        >  によって送信操作 (またはカテゴリ) を選択、複数の 1 つの WCF クライアント クラスが生成されます。 詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
3.  ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
    1.  をクリックして**オプションの高度な**を開くには、**オプションの高度な**ボックス。  
  
    2.  **オプションの高度な**下にあるボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択することができます。  
  
    3.  **シリアライザー**のために使用されるシリアライザーを選択します。  
  
     次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーしない他のオプションが選択されているため)。  
  
     ![高度なオプション ボックスの既定の設定](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
     構成できるオプション、**オプションの高度な**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスが使用可能なオプションの一部に相当します。 これらのオプションの詳細については、次を参照してください。 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)です。
  
4.  **[OK]**をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラス (または WCF サービスのインターフェイス) を保存し、操作と、プロジェクト ディレクトリに選択したカテゴリのヘルパー コード。 既定では、構成ファイルも保存されます。 受信と送信操作です。 わずかに異なるファイルが生成されます。詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
 記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択します。 たとえば、すべての操作を AR_ARCHIVE_PURGE_INTERIM テーブルの表示用の WCF クライアントを生成することができますを選択する、 **AR_ARCHIVE_PURGE_INTERIM**ノード。  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)