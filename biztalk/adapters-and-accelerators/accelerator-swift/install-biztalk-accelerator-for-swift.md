---
title: BizTalk Accelerator を SWIFT のインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- documentation
ms.assetid: 8d492248-fde6-4fd8-be6b-e86ac7d0808b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e28d5dac74bdbceb0fe4938810779d6ccb5c52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-accelerator-for-swift"></a>BizTalk Accelerator を SWIFT をインストールします。
インストール[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]の BizTalk Server にします。 

\<!---前のテキスト
-   [BizTalk Accelerator for SWIFT のインストール ガイド](http://go.microsoft.com/fwlink/?LinkId=198120)    
-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Readme、\Program Files\Microsoft BizTalk Accelerator for SWIFT の \Documentation フォルダーにあります。  
-->

## <a name="hardware-and-software-requirements"></a>ハードウェアとソフトウェアの要件

ハードウェアとソフトウェアの最小要件は、同じ[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。

|  |BizTalk の要件  |SQL と OS の要件 |  
|---------|---------|--------- | 
| [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [BizTalk Server 2016 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) | **SQL Server のハードウェアおよびソフトウェア要件**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows サーバーのハードウェア要件**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx) |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [BizTalk Server 2013 および 2013 R2 のハードウェアおよびソフトウェア](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) |**SQL Server のハードウェアおよびソフトウェア要件**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows サーバーのハードウェア要件**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)  |

> [!TIP] 
> ここにリストされているのは最小のハードウェア要件です。 環境はそれぞれ異なり、ご使用の環境ではこれらを超える要件が必要となる可能性は十分あります。 「[BizTalk Server ソリューションのインストール、サイズ変更、配置、およびメンテナンスを行うための推奨事項](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)」を参照してください。 

## <a name="install-swift"></a>SWIFT をインストールします。

### <a name="before-you-begin"></a>アンインストールの準備

* メンバーであるアカウントでサインインする、BizTalk Server 管理者グループ。 
* BizTalk Server のダウンロード、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]のセットアップ、`\BizTalk Accelerators`フォルダーです。
* BizTalk Server をインストールする必要があります、SQL Server を実行する必要があります。
* サイレント インストールはサポートしますが、必要とされる追加の構成手順が複雑なのためお勧めできません。
* A4SWIFT セットアップは、常にで動作、`/InstallPlatform`引数。 結果として、常に msvcr71.dll、mfc71u.dll、msvcp71.dll、およびインストール atl71.dll は Visual Studio の必要なです。 これらの DLL ファイルをインストール、`%WINDIR%\System32`フォルダー、かどうか、Dll 前にインストールされたか。

### <a name="default-installation"></a>既定のインストール

1. 実行、 [!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe**管理者として。
2. **[インストール]**を選択します。
3. **[ユーザー名]**、**[組織]**、およびプロダクト キーを入力します。 **[次へ]** を選択します。
4. ライセンス契約を読み、クリックして**Accept**です。
5. 選択**完了**、し、**次**です。
6. 確認、**概要**ページ。 変更するには、次のように選択します。**戻る**です。

    システム再起動後に自動的にログオンするには、**[設定]** を選択して、サインイン アカウントを入力します。 これは、セットアップ中にのみ有効です。 セットアップが完了すると、この設定は無効になります。

    **[インストール]**を選択します。
 
7. 選択**完了**を完了するとします。 ような一時フォルダーにセットアップ ログ ファイルを生成:`C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`です。

> [!NOTE] 
> 場合**構成ウィザードの実行**がインストールの完了 ページで、選択されている、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]をクリックしたときに、構成ウィザードが自動的に実行されます**完了**です。 


### <a name="custom-installation"></a>カスタム インストール

1. 実行、 [!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe**管理者として。
2. **[インストール]**を選択します。
3. **[ユーザー名]**、**[組織]**、およびプロダクト キーを入力します。 **[次へ]** を選択します。
4. ライセンス契約を読み、クリックして**Accept**です。
5. 選択**カスタム**、し、**次**です。
6. コンポーネントを選択してから**次**:

    | 選択するオプション | 目的 |
    | --- | --- |
    | A4Swift のコンポーネント | BizTalk Server に SWIFT メッセージの処理 (スキーマの解決、解析、検証) するために必要 |
    | メッセージの修復と調整 | パイプライン、オーケストレーション、および実行時のスキーマをインストールします。 SQL Server のメッセージング、修復、および調整の A4SWIFT データベースを作成します。 |
    | メッセージ repair and new submission の web コンポーネント | Message Repair and New Submission の web サービスを検証、証明書のセキュリティ、履歴、および BIC 参照を作成するのには、コンポーネントをインストールします。 |
    | ソフトウェア開発キット (SDK) | Visual Studio のサンプル ソース コード、ツールキット、および starter プロジェクトが含まれています。 | 
    | BRE 配置ユーティリティ | 既に展開されている SWIFT のメッセージの種類に関連付ける、ビジネス ルール エンジン (BRE) ポリシーを配置するためのユーティリティ。 |
    | チュートリアル | Iincludes 指示と BizTalk Server では、迅速なソリューションを開発するためのサンプルです。 |
    | ツール | A4SWIFT の開発用ツールが含まれます。 |
    | ソース | A4SWIFT の開発のソース コードのサンプルをインストールします。 |
    
6. 確認、**概要**ページ。 変更するには、次のように選択します。**戻る**です。

    **[インストール]**を選択します。
 
7. 選択**完了**を完了するとします。 ような一時フォルダーにセットアップ ログ ファイルを生成:`C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`です。

> [!NOTE]
> 場合**構成ウィザードの実行**がインストールの完了 ページで、選択されている、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]をクリックしたときに、構成ウィザードが自動的に実行されます**完了**です。 

## <a name="next-steps"></a>次の手順
[SWIFT の BizTalk アクセラレータを構成します。](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)