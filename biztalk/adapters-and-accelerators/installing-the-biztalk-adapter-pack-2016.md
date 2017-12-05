---
title: "BizTalk Adapter Pack 2016 のインストール |Microsoft ドキュメント"
description: "BAP 2016、32 ビットと 64 ビットの標準またはカスタムのインストールはサイレント モードでインストールします。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f3e1717-8063-4460-bfdc-a933cd58a5c1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7076b9c076b263a54a436c553b519671760ca473
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-biztalk-adapter-pack-2016"></a>BizTalk Adapter Pack 2016 をインストールします。
インストール、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次の 2 つの方法で。  
  
-   **対話モードで**: セットアップ ウィザードを実行  
  
-   **サイレント モードで**: コマンドラインを使用して  
  
> [!IMPORTANT]
> - インストールするコンピューターで管理者特権を持つ必要があります、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ウィザードまたはコマンドラインを使用してをインストールするかどうかのあるかにかかわらず、します。  
> - すべてのことを確認する、[ソフトウェアの前提条件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)がインストールする前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。

## <a name="typical-vs-custom-installation"></a>標準セットアップとカスタム インストール  
インストールの種類と各オプションでインストールされている機能の一覧を示します。  
  
-   **標準**と**完了**オプションは、関連付けられているデータ プロバイダーとすべてのアダプターをインストールします。 インストールする特定のアダプターを選択するオプションがありません。  
  
-   **カスタム**オプションは、関連付けられているデータ プロバイダーと 1 つまたは複数のアダプターをインストールします。 インストールするには、どのアダプターを選択できます。 データ プロバイダーをインストールする場合は、また、対応するアダプターをインストールする必要があります。 ただし、対応するデータ プロバイダーをインストールしなくても、アダプターをインストールすることができます。 これには、展開、 **ADO プロバイダー**ノード、およびインストールしたくないプロバイダーを選択します。 参照してください**セットアップ ウィザードを使用してインストール**(」を参照)。  
  
     たとえば、インストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]もインストールする必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]です。 ただし、インストールすることができます、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]インストールしなくても、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。  
  
## <a name="32-bit-and-64-bit-install-scenarios"></a>32 ビットおよび 64 ビット インストール シナリオ
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]に使用できます。 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]デザイン時 (場合、LOB アプリケーションでの操作のメタデータの生成)
  
-   BizTalk Server 管理コンソール デザイン時 (物理ポートの作成)
  
    > [!NOTE]
    >  BizTalk Server 管理コンソールは、32 ビット Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。  
  
-   BizTalk ランタイム (ときに送信し、LOB アプリケーションからメッセージを受信)

これらすべての検索の 1 台のコンピューターを使用したり、別のコンピューターを使用することができます。 両方[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]と BizTalk MMC は 32 ビット プロセスが、32 ビットをインストールする必要があります[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]デザイン時のタスクを完了するコンピューターにします。 

### <a name="32-bit-install-scenario"></a>32 ビット インストール シナリオ
各コンピューターで、次のソフトウェアをインストールします。 1 台のコンピューターを使用している場合、そのコンピューターにすべてのソフトウェアをインストールする必要があります。 
 
1. 32 ビットをインストールします。[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]
2. 32 ビット インストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。
3. 32 ビットのインストールの LOB クライアントおよびその他の Dll が必要です。  
  
### <a name="64-bit-install-scenarios"></a>64 ビット インストール シナリオ
  
|Visual Studio のデザイン時の|MMC の BizTalk のデザイン時|Biztalk ランタイム|Visual Studio のデザイン時およびデザイン時の BizTalk MMC + BizTalk 実行時間|  
|---|---|---|---|  
|がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|**32 ビット BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 64 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> -64 ビット LOB クライアントとその他の必要な Dll をインストールします。|**32 ビット BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセス**:<br /><br /> がインストール 64 ビット[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]です。<br /><br /> がインストール 64 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> -64 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> がインストール 32 ビット[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。|  
  
> [!NOTE]
>  デザイン時のタスクを実行する任意のコンピューターでいずれかの操作を使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。  
  
## <a name="install-using-the-setup-wizard"></a>セットアップ ウィザードを使用したインストールします。  
インストールする手順、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モードでします。  
  
1.  実行、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**です。  
  
2.  選択**Microsoft BizTalk Adapters インストール**です。 次のウィンドウで、前提条件のすべての不足しているプログラムが一覧表示されます。 いずれかが存在しない場合、不足しているプログラムを選択し、セットアップでは、それをインストールします。 

    たとえば、選択**手順 2: Microsoft BizTalk Adapter Pack のインストール**または**手順 3: インストール Microsoft BizTalk Adapter Pack (x64)**です。  
  
    > [!NOTE]
    >  インストールする場合、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]バーチャル マシンでは、セットアップ ウィザードの使用可能なディスク領域をチェックするメッセージが表示されます。 ハングまたはただ座っていて、このメッセージが表示されるかどうかは、ことをお勧め**サイレント モードでインストール**(」を参照)。  
  
3.  [ようこそ] 画面で、次のように選択します。**次**です。  
  
4.  使用許諾契約書 (EULA) に同意し、**次**です。  
  
5.  **セットアップの種類を選択して**:  
  
    -   最も一般的な機能をインストールする選択**標準**です。  
  
    -   インストールするアダプターを選択するには、次のように選択します。**カスタム**、し、次の手順に進みます。  
  
    -   すべての機能をインストールする選択**完了**です。  
  
        > [!IMPORTANT]
        >  エンタープライズ アプリケーションとのインターフェイスで、選択に使用するアダプターのみをインストールする、**カスタム**インストールします。  
  
6. **必要な**カスタム インストールを選択した場合のみです。 選択した場合、**標準**または**完了**インストールし、この手順をスキップし、手順 7. に進みます。  
  
    1.  **カスタム セットアップ**、展開**ベース アダプター**に利用可能なアダプターを参照してください。  
  
    2.  必要のないアダプターの場合、アダプターの横にあるアイコンを選択し、**全体の機能は使用できません**です。  
  
    3.  展開**ADO プロバイダー**、しをインストールしたくないプロバイダーを選択します。  
  
    4.  **[次へ]** を選択します。  
  
7.  **[インストール]**を選択します。  
  
8.  **カスタマー エクスペリエンス向上プログラム**、登録することもできます。 登録する場合は、Microsoft と、次のデータを共有できます。  
  
    -   インストールしているコンピューターのハードウェアに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。  
  
    -   使用するエンタープライズ アプリケーションのバージョンに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。  
  
     [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)詳しく説明します。  
     
     **[OK]** を選択します。 
  
    > [!NOTE]
    >  修復モードで、セットアップを実行して、この設定を変更することが常に**プログラム**です。  
  
9. **[完了]** を選択します。  
  
<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a>サイレント モードでインストールします。  
 使用して、 **msiexec**サイレント インストールを実行するコマンド。 Msiexec コマンドの一部としてインストールする個々 のコンポーネントを入力します。 次の表に、内の各コンポーネントの値、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。 特定のコンポーネントをインストール (または削除) するのにには、これらの値を使用します。 ホスト インスタンスをインストール (または削除) するには、複数のコンポーネントは、コンマ区切りでこれらの値の組み合わせを使用できます。  
  
|コンポーネント名|コマンド ライン プロパティの対応する値|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|DbFeature|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|OracleEBSFeature|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|SapBaseAdapterFeature|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|SiebelBaseAdapterFeature|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|SqlFeature|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|SapAdoFeature<br /><br /> **注**: インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]もします。|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|SiebelAdoFeature<br /><br /> **注**: インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]もします。|  
|すべてのコンポーネント|ALL|  
  
> [!IMPORTANT]
>  機能名は大文字小文字を区別します。  
  
 次の手順は、のサイレント インストールを完了する方法を示します[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]さまざまなコンポーネントです。  
  
### <a name="silent-mode-steps"></a>サイレント モードの手順
  
1.  コマンド プロンプトを開きに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]でルート、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。  
  
2.  インストールする内容に基づいて、次のコマンドを実行します。  
  
    > [!NOTE]
    >  X64 ベースのプラットフォームでのサイレント インストールには、置換`AdaptersSetup.msi`で`AdaptersSetup64.msi`次のコマンドにします。  
  
    -   アダプターは、.NET Framework データ プロバイダーを含む、すべてをインストールする完全なインストールを実行するには、次のように入力します。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   インストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]と共に[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   インストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]と共に[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   のみをインストールする、[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]種類。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   すべてのベース アダプターをインストールするには、次のように入力します。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   2 つの .NET Framework データ プロバイダーをインストールするには、次のように入力します。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   コンマで区切って、コンポーネントでカスタム インストールのすべての型。 たとえば、インストールするため、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]で、 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、および[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]型。  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   CEIP をサイレント インストールの一部として登録することもできます。 型:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         既定では、オプションは false です。 
  
        > [!IMPORTANT]
        >  インストール中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでの評価版、CEIP の既定のオプションが true です。  
  
     詳細については、 **msiexec**コマンドで、入力`msiexec`キーを押して、コマンド ライン`ENTER`です。 移動または[http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)です。
     
## <a name="known-install-issue"></a>インストールの既知の問題
包括のインストールに関連する問題の一覧を表示するを参照してください**トラブルシューティング**アダプターごとにトピックです。  
  
**64 ビット コンピューターでセットアップを実行してはスキーマ ファイルにアクセス中にエラーをスローする可能性があります。**  
  
[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップによって、Microsoft.Adapters へのアクセス中にエラーがスローされます*。\<AdapterName\>*_schema.xml ファイルが、アダプターのインストールを続行します。  
  
**原因**  
  
場合は 32 ビットと 64 ビットの両方のバージョン、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]がインストールされている同じコンピューター両方で使用されるターゲットのスキーマ ファイルは同じです。 その結果、ファイルは、32 ビットでインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]64 ビットのインストーラーが、アクセスしようとするときに、IIS によって使用されている可能性があります。  
  
**解決策**  
  
Microsoft.Adapters を手動でコピーします。 *\<AdapterName\>*_schema.xml ファイルから*C:\Program files \microsoft BizTalk Adapter Pack (x64) \IIS スキーマ*に*C:\Windows\System32\inetsrv\config\schema*です。 
  
## <a name="next-step"></a>次の手順
[ポスト インストール手順](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)