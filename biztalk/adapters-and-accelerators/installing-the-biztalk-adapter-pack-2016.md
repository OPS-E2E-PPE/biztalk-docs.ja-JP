---
title: BizTalk Adapter Pack 2016 のインストール |Microsoft Docs
description: BAP 2016、32 ビットと 64 ビットの標準またはカスタムのインストールはサイレント モードでインストールします。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f3e1717-8063-4460-bfdc-a933cd58a5c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ccbffa606db9f26448ee74198eeb4ec67bee94d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363962"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a>BizTalk Adapter Pack 2016 をインストールします。
インストール、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]次の 2 つの方法で。  

-   **対話モードで**:セットアップ ウィザードを実行します。  

-   **サイレント モードで**:コマンドラインを使用してください。  

> [!IMPORTANT]
> - インストールするコンピューターで管理者特権が必要、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]ウィザードまたはコマンドラインを使用してをインストールするかどうかに関係なく、します。  
> - すべてのことを確認する、[ソフトウェアの前提条件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)がインストールする前にインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。

## <a name="typical-vs-custom-installation"></a>一般的な vs カスタム インストール  
インストールの種類と各オプションでインストールされている機能を示します。  

- **標準**と**完了**オプションは、関連付けられているデータ プロバイダーを使用したすべてのアダプターをインストールします。 特定のアダプターを選択するをインストールするオプションはありません。  

- **カスタム**オプションは、関連付けられているデータ プロバイダーを使用した 1 つまたは複数のアダプターをインストールします。 インストールするアダプターを選択できます。 データ プロバイダーをインストールする場合は、対応するアダプターをインストールする必要もあります。 ただし、対応するデータ プロバイダーをインストールしなくても、アダプターをインストールすることができます。 これには、展開、 **ADO プロバイダー**ノードを展開し、インストールしないプロバイダーを選択します。 参照してください**セットアップ ウィザードを使用してインストール**(」を参照)。  

   たとえばをインストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]もインストールする必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]します。 ただし、インストールすることができます、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]インストールしなくても、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]します。  

## <a name="32-bit-and-64-bit-install-scenarios"></a>32 ビットおよび 64 ビット インストール シナリオ
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]に使用できます。 

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] デザイン時 (場合、LOB アプリケーションでの操作のメタデータの生成)

- BizTalk Server 管理コンソールのデザイン時 (を物理ポートを作成)

  > [!NOTE]
  >  BizTalk Server 管理コンソールは、32 ビットの Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。  

- BizTalk の実行時間 (LOB アプリケーションからメッセージを送受信) するときに

1 台のコンピューターを使用して、これらすべての検索のまたは異なるコンピューターを使用できます。 両方[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC は 32 ビット プロセスとは、32 ビットをインストールする必要があります[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]デザイン時の作業を実行するコンピューター。 

### <a name="32-bit-install-scenario"></a>32 ビット インストール シナリオ
各コンピューターに、次のソフトウェアをインストールします。 1 台のコンピューターを使用している場合、そのコンピューターにすべてのソフトウェアをインストールする必要があります。 

1. 32 ビットをインストールします。 [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]
2. 32 ビット インストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。
3. 32 ビット LOB クライアントのインストール、およびその他の Dll が必要です。  

### <a name="64-bit-install-scenarios"></a>64 ビット インストール シナリオ

|                                                                                                                 Visual Studio のデザイン時の                                                                                                                  |                                                                                                                  BizTalk MMC のデザイン時                                                                                                                   |                                                                                                                                                                                                                                                                                                         Biztalk ランタイム                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                Visual Studio のデザイン時またはデザイン時の BizTalk MMC + BizTalk 実行時間                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 | -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 | **32 ビット BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -64 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> -64 ビットの LOB クライアントとその他の必要な Dll をインストールします。 | **32 ビット BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> **64 ビットの BizTalk プロセスの**:<br /><br /> -64 ビットのインストール[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]します。<br /><br /> -64 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> -64 ビットの LOB クライアントとその他の必要な Dll をインストールします。<br /><br /> -32 ビットのインストール[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。<br /><br /> 32 ビット LOB クライアントとその他の必要な Dll をインストールします。 |

> [!NOTE]
>  デザイン時のタスクを実行する任意のコンピューターにいずれかを使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  

## <a name="install-using-the-setup-wizard"></a>セットアップ ウィザードを使用してインストールします。  
インストールする手順、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]対話モードでします。  

1. 実行、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**します。  

2. 選択**Microsoft BizTalk Adapters インストール**します。 次のウィンドウで、不足している前提条件となるプログラムの一覧が表示されます。 いずれかが存在しない場合は、不足しているプログラムを選択し、セットアップでは、それをインストールするします。 

   たとえば、**手順 2。Microsoft BizTalk Adapter Pack をインストール**または**手順 3。Microsoft BizTalk Adapter Pack (x64) をインストール**します。  

   > [!NOTE]
   >  インストールする場合、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]バーチャル マシンの場合は、セットアップ ウィザードの使用可能なディスク領域をチェックするメッセージが表示されます。 かどうかは、ハング、またはただ座っていて、このメッセージが表示されますすることが推奨**サイレント モードでインストール**(」を参照)。  

3. [ようこそ] 画面で、次のように選択します。**次**します。  

4. 使用許諾契約書 (EULA) に同意し、**次**します。  

5. **セットアップの種類を選択**:  

   -   最も一般的な機能をインストールする選択**標準**します。  

   -   インストールするアダプターを選択するには、次のように選択します。**カスタム**、し、次の手順に進んでください。  

   -   すべての機能をインストールする選択**完了**します。  

       > [!IMPORTANT]
       >  エンタープライズ アプリケーションとのインターフェイスを選択し、使用するアダプターのみをインストールする、**カスタム**インストールします。  

6. **必要な**カスタム インストールを選択した場合のみです。 選択した場合、**標準**または**完了**インストールでは、次に、この手順をスキップし、手順 7. に進みます。  

    1.  **カスタム セットアップ**、展開**ベース アダプター**に使用可能なアダプターを参照してください。  

    2.  しないようにするアダプターの場合、アダプターの横にあるアイコンを選択し、**全体の機能は使用できません**します。  

    3.  展開**ADO プロバイダー**、し、インストールしないプロバイダーを選択します。  

    4.  **[次へ]** を選択します。  

7. **[インストール]** を選択します。  

8. **カスタマー エクスペリエンス向上プログラム**、登録することもできます。 を登録する場合は、Microsoft と、次のデータを共有できます。  

   - インストール先コンピューターのハードウェアに関連するデータ、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  

   - 関連データを使用するエンタープライズ アプリケーションのバージョンを[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  

     [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699)詳細に説明します。  

     **[OK]** を選択します。 

   > [!NOTE]
   >  修復モードでセットアップを実行して、この設定を変更することが常に**プログラム**します。  

9. **[完了]** を選択します。  

<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a>サイレント モードでインストールします。  
 使用して、 **msiexec**サイレント インストールを実行するコマンド。 Msiexec コマンドの一部として、インストールする個々 のコンポーネントを入力します。 次の表に、内の各コンポーネントの値、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。 特定のコンポーネントをインストール (または削除) するのにには、これらの値を使用します。 1 つ以上のコンポーネントをインストール (または削除)、コンマで区切られたこれらの値の組み合わせを使用できます。  


|                                    コンポーネント名                                    |                                                                コマンド ライン プロパティの対応する値                                                                 |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        |                                                                                   DbFeature                                                                                    |
| [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] |                                                                                OracleEBSFeature                                                                                |
|           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |                                                                             SapBaseAdapterFeature                                                                              |
|        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |                                                                            SiebelBaseAdapterFeature                                                                            |
|            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |                                                                                   SqlFeature                                                                                   |
|        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |     SapAdoFeature<br /><br /> **注**:インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]もします。      |
|     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | SiebelAdoFeature<br /><br /> **注**:インストールする場合にのみ、この値を指定する必要があります、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]もします。 |
|                                    すべてのコンポーネント                                    |                                                                                      ALL                                                                                       |

> [!IMPORTANT]
>  機能名は大文字小文字を区別します。  

 次の手順は、のサイレント インストールを完了する方法を説明[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]さまざまなコンポーネントです。  

### <a name="silent-mode-steps"></a>サイレント モードの手順

1. コマンド プロンプトを開きに移動、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]でルート、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。  

2. インストールする内容に基づいて、次のコマンドを実行します。  

   > [!NOTE]
   >  X64 ベースのプラットフォームでサイレント インストールには、置換`AdaptersSetup.msi`で`AdaptersSetup64.msi`で、次のコマンド。  

   - アダプターは、.NET Framework データ プロバイダーを含む、すべてをインストールする完全なインストールを実行するには、次のように入力します。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
     ```  

   - のみをインストールする、[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
     ```  

   - のみをインストールする、[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
     ```  

   - のみをインストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
     ```  

   - インストールする、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]と共に[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
     ```  

   - のみをインストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
     ```  

   - インストールする、[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]と共に[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
     ```  

   - のみをインストールする、[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]種類。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
     ```  

   - 基本のすべてのアダプターをインストールするには、次のように入力します。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
     ```  

   - 2 つの .NET Framework データ プロバイダーをインストールするには、次のように入力します。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
     ```  

   - コンマでコンポーネントを分離することで、カスタム インストールの任意の型。 たとえば、インストールするため、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]で、 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]、および[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]型。  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
     ```  

   - サイレント インストールの一環として、CEIP に登録することもできます。 型:  

     ```  
     msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
     ```  

      既定では、オプションは false です。 

     > [!IMPORTANT]
     >  インストール中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]サイレント モードでの評価版、CEIP の既定のオプションは true。  

     詳細については、 **msiexec**のコマンドを入力`msiexec`コマンドライン、およびキーを押して`ENTER`します。 移動または[ http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199)します。

## <a name="known-install-issue"></a>インストールの既知の問題
インストールに関連する問題の包括的な一覧を参照してください**トラブルシューティング**アダプターごとにトピック。  

**64 ビット コンピューターでセットアップを実行してはスキーマ ファイルにアクセス中にエラーをスローする可能性があります。**  

[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ、Microsoft.Adapters へのアクセス中にエラーをスローします *。\<AdapterName\>*_schema.xml ファイルが、アダプターのインストールを続行します。  

**原因**  

場合の 32 ビットと 64 ビットの両方のバージョン、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]がインストールされている両方で使用されるターゲットのスキーマ ファイルでは、同じコンピューターでは同じです。 32 ビットでファイルがインストールされている結果として、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 64 ビットのインストーラーが、アクセスしようとしています。 IIS で使用されている可能性があります。  

**解決方法**  

Microsoft.Adapters を手動でコピーします。 *\<AdapterName\>*_schema.xml ファイルから*C:\Program files \microsoft BizTalk Adapter Pack (x64) \IIS スキーマ*に*C:\Windows\System32\inetsrv\config\schema*します。 

## <a name="next-step"></a>次の手順
[インストール後の手順](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)