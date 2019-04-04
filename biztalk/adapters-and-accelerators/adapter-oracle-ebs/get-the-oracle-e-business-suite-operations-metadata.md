---
title: Oracle E-business Suite 操作のメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 566ae086-183a-47db-8f93-12b5903c85c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8904a70d2bfe1b34b28b7cad807796fac752009
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014843"
---
# <a name="get-the-oracle-e-business-suite-operations-metadata"></a>Oracle E-business Suite 操作のメタデータを取得します。
使用することができます、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Oracle E-business Suite の成果物を選択したスキーマを生成します。 参照を呼び出したいアイテムを検索した後、それらの成果物のスキーマを生成し、Oracle E-business Suite へのスキーマに準拠したメッセージを送信できます。  
  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
## <a name="prerequisites"></a>前提条件  
 対象の操作のメタデータを取得する前に、Oracle E-business Suite に接続する必要があります。 使用する時に、データベース、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)します。  
  
## <a name="generating-schema-using-the-consume-adapter-service-add-in"></a>使用してスキーマを生成する、アダプターを使用する追加のサービス  
  
> [!NOTE]
>  そのカテゴリのサブ-ツリー内のすべての操作を取得するカテゴリ ノードを選択することができます: たとえば、選択、**同時実行プログラム**(Oracle アプリケーションの同時実行プログラムがすべてのスキーマの生成) するノードまたはすることができます同時実行の特定のプログラムを選択します。 ノードの詳細については、メタデータ ノード Id を参照してください。  
  
#### <a name="to-generate-schema-for-oracle-e-business-suite-artifacts"></a>Oracle E-business Suite の成果物のスキーマを生成するには  
  
1. Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
   > [!IMPORTANT]
   >  使用して操作を実行するためのスキーマを生成する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]設定する必要があります、 **EnableBizTalkCompatibilityMode**プロパティをバインド**True**します。 Oracle E-business Suite への接続を確立中には、このバインドのプロパティを設定する必要があります。  
  
2. **選択コントラクト型**一覧で、受信または送信操作のスキーマを生成するかどうかに基づく契約の種類を選択します。  
  
3. メタデータを生成するカテゴリ ノードをクリックします。 たとえば、Oracle アプリケーション内で同時実行プログラムのメタデータを生成する場合は、クリックして**同時実行プログラム**します。  
  
4. カテゴリのノードを展開し、メタデータを生成する、そのノード内の特定の項目を選択します。 たとえば、"銀行 Center"アプリケーションの同時実行プログラムのメタデータを生成するには、次のように展開します。、**同時実行プログラム**ノード、およびクリック**バンキング Center**します。  
  
5. **利用可能なカテゴリと操作**ボックスを起動し をクリックする操作を選択**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。 たとえば、「FTP 銀行の削除アカウント」と"Get_Status"同時実行プログラムを起動する操作の名前をクリック**追加**します。  
  
    次に示します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、選択した操作が一覧表示されます。  
  
    ![Oracle E からメタデータを取得&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/df7de132-9177-4de7-a620-59dbd561efe5.gif "df7de132-9177-4de7-a620-59dbd561efe5")  
  
    複数の操作のスキーマを生成する場合は、いくつかで BizTalk プロジェクトのコンパイル エラーを引き起こす可能性のあるこれらのスキーマ間で重複する要素の定義である可能性があります。 たとえば、"Op1"操作のスキーマを生成するシナリオを検討してください。 "Op1"のスキーマには、データ型"CT1"のパラメーターが含まれています。 閉じる"Op1"のスキーマを生成した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]し、もう一度開き、別の操作"Op2"のスキーマを生成します。 "Op2"も"CT1"のデータ型のパラメーターが含まれていると仮定します。 終了した後、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]とプロジェクトをコンパイル、複雑なデータ型"CT1"が別の XSD ファイルで 2 回定義されているため、コンパイル エラーが発生します。 このような状況には、次のお勧めします。  
  
   - 1 つの実行ですべての操作のスキーマを生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 これにより、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] "CT1"複雑なデータ型の 1 つだけ定義が生成されます。  
  
   - 複数の異なる実行で複数の操作のスキーマを生成する[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を選択するかどうかを確認、**一意のスキーマ型を生成**生成された XSD ファイルの一意の名前空間に含まれるようにチェック ボックスをオン、複雑なデータは、"CT1"を入力します。  
  
6. **[OK]** をクリックします。 スキーマ ファイルは、BizTalk プロジェクトと同じ場所にある拡張子が .xsd で保存されます。  
  
   > [!NOTE]
   >  Oracle アーティファクトに対する操作のメタデータを生成する Consume Adapter Service アドインを使用している場合は、既定では、ファイルが作成特定の名前付け規則: 生成された XSD ファイルの名前が次の 3 つの部分。  
   > 
   > - 提供される"OracleEBSBinding"またはプレフィックス、**ファイル名のプレフィックス**ボックス。  
   >   - 含まれる名、 **fileNameHint**で生成される WSDL 注釈タグ。 操作の場合は、ファイル名のヒントは、操作のグループと同じです。 複合型では、ファイル名のヒントは、名前空間なし、"<http://schemas.microsoft.com/OracleEBS/2008/05/”>プレフィックス。 インターフェイス テーブル操作のファイル名のヒントは規則に従ってなど\<InterfaceTables\>+ < app_short_name > + < interface_table_name >。  
   >   - (省略可能)ファイル名が一意であることを確認する整数。  
   > 
   >   最後に XSD ファイルの名前が < file_name_prefix > としてに到着した +\<fileNameHint\>+ n、"n"は一意の整数です。  
   > 
   > [!NOTE]
   >  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ときに指定されたバインドのプロパティを含むバインド ファイル (XML ファイル) も作成操作と操作を呼び出すための SOAP アクションのスキーマを生成します。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]バインドのプロパティと SOAP アクションの接続 URI で WCF カスタム ポートを作成する管理コンソールで設定します。 詳細については、[Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)を参照してください。  
  
    Oracle E-business Suite の成果物のメタデータが正常に生成されました。 メタデータを使用すると、特定の操作を実行するのに Oracle E-business Suite にメッセージを送信します。 参照してください[Oracle E-business Suite アダプターを使用して開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)これらの操作を実行する方法の詳細について。  
  
## <a name="generating-a-wcf-client-or-wcf-service-contract-using-the-add-adapter-service-reference-plug-in"></a>WCF クライアントまたは WCF サービス コントラクトを使用して、生成、プラグインのアダプター サービス参照の追加  
 使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]いずれかの送信操作の WCF クライアント コードまたは受信操作のための WCF サービス コードを生成します。  
  
#### <a name="to-generate-wcf-client-class-or-service-contract-for-oracle-e-business-suite-operations"></a>Oracle E-business Suite 操作のための WCF クライアント クラスまたはサービス コントラクトを生成するには  
  
1. [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]から、**コントラクト型を選択します**ドロップダウン リストで、かどうかを実行する受信または送信の操作に基づく契約の種類を選択します。  
  
2. 参照または (インターフェイス テーブル) などのカテゴリまたは特定の WCF クライアント (または WCF サービス コントラクト) を生成する操作を検索します。   
   AR_ARCHIVE_PURGE_INTERIM インターフェイス テーブルに対する操作の参照など、**カテゴリを選択**ボックス。  
  
   1. ルート ノードを展開 (**/**) を Oracle E-business suite 操作が表示されるカテゴリを表示します。 同じインターフェイス テーブルは 使用できる、**アプリケーション ベースのビュー**ノードだけでなく**成果物ベースのビュー**ノード。 この例からの WCF クライアント クラスを生成、**アプリケーション ベースのビュー**ノード。  
  
   2. [ルート] ノードで、展開、**アプリケーション ベースのビュー** Oracle E-business Suite で使用可能なアプリケーションを表示するノード。  
  
   3. ノードを展開、 **Receivables**アプリケーションを展開し、**インターフェイス テーブル**ノード。  
  
   4. をクリックして、 **AR_ARCHIVE_PURGE_INTERIM**インターフェイス テーブルのノードと、**利用可能なカテゴリと操作**ボックスで、WCF クライアント (または WCF サービスを生成する操作を選択します。コントラクト) をクリックして**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
       次に示します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]選択 AR_ARCHIVE_PURGE_INTERIM テーブルの Insert と Select 操作とします。  
  
       ![WCF クライアントまたはサービス コントラクトの生成](../../adapters-and-accelerators/adapter-oracle-ebs/media/oraebs-adap-add-adap-serv-refs.gif "oraebs_adap_add_adap_serv_refs")  
  
      > [!IMPORTANT]
      >  によって送信操作 (またはカテゴリ) を選択で、複数の 1 つの WCF クライアント クラスを生成できます。 詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。  
  
3. ほとんどのシナリオで、既定のシリアル化オプションで十分です。ただし、必要な場合は、生成されたコードに関するいくつかの側面と使用されるシリアライザーの型を制御できます。 これらのオプションを設定するには  
  
   1. をクリックして**詳細オプション**を開く、**詳細オプション**ボックス。  
  
   2. **オプションの高度な**ボックス**生成されたプロキシのオプションを選択**、必要なオプションを選択します。 たとえば、非同期メソッドは、WCF クライアントの生成または構成ファイルの生成を無効にするかどうかを選択できます。  
  
   3. **シリアライザー**使用されるシリアライザーを選択します。  
  
      次に示します、**オプションの高度な**ボックスに、既定の選択 (**自動**が選択されているシリアライザーとしないその他のオプションが選択されているため)。  
  
      ![高度なオプションが既定の設定をボックス](../../adapters-and-accelerators/adapter-oracle-database/media/r2-net-adapters-oracle-msb-advanced-options.gif "R2_NET_Adapters_Oracle_MSB_Advanced_Options")  
  
      オプションで構成できる、**詳細オプション**ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用する場合は、ボックスはいくつかの使用可能なオプションに相当します。 これらのオプションの詳細については、[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)を参照してください。
  
4. **[OK]** をクリックします。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF クライアント クラス (または WCF サービスのインターフェイス) を保存し、操作と、プロジェクト ディレクトリで選択したカテゴリのヘルパー コード。 既定では、構成ファイルも保存されます。 受信と送信操作の若干異なるファイルが生成されます。詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。  
  
   記載されている任意のノードを選択することができます、**利用可能なカテゴリと操作**ボックス。 カテゴリ ノードを選択する場合は、すべてのノードとそのサブ ノードで使用可能な操作が選択されます。 たとえば、AR_ARCHIVE_PURGE_INTERIM テーブルの表示操作のすべての WCF クライアントを生成するを選択、 **AR_ARCHIVE_PURGE_INTERIM**ノード。  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)