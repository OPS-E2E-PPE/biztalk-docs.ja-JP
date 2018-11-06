---
title: BizTalk Accelerator を SWIFT のインストール |Microsoft Docs
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
ms.openlocfilehash: 101d3600bbe38115bb20983e84ddd9192f8daf00
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752690"
---
# <a name="install-biztalk-accelerator-for-swift"></a>BizTalk Accelerator を SWIFT をインストールします。
インストール[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]BizTalk Server にします。 

\<!---以前のテキスト
- [BizTalk Accelerator for SWIFT のインストール ガイド](http://go.microsoft.com/fwlink/?LinkId=198120)    
- Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] \program files BizTalk Accelerator for SWIFT の \Documentation フォルダー Readme。  
  -->

## <a name="hardware-and-software-requirements"></a>ハードウェアとソフトウェアの要件

ハードウェアとソフトウェアの最小要件は同じ[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。


|                                                                                                                                                                   |                                                                                BizTalk の要件                                                                                 |                                                                                                                                                                                                                                                            SQL と OS の要件                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                       [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]                                                        |             [BizTalk Server 2016 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)             |                                      **SQL Server のハードウェアおよびソフトウェア要件**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows サーバーのハードウェア要件**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)                                      |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) | **SQL Server のハードウェアおよびソフトウェア要件**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows サーバーのハードウェア要件**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx) |

> [!TIP] 
> ここにリストされているのは最小のハードウェア要件です。 環境はそれぞれ異なり、ご使用の環境ではこれらを超える要件が必要となる可能性は十分あります。 「[BizTalk Server ソリューションのインストール、サイズ変更、配置、およびメンテナンスを行うための推奨事項](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)」を参照してください。 

## <a name="install-swift"></a>SWIFT をインストールします。

### <a name="before-you-begin"></a>アンインストールの準備

* BizTalk Server 管理者グループのメンバーであるアカウントを使用してサインインします。 
* BizTalk Server のダウンロード、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]のセットアップ、`\BizTalk Accelerators`フォルダー。
* BizTalk Server をインストールする必要があります、および SQL Server を実行する必要があります。
* サイレント インストールはサポートされていますが、必要な追加の構成手順の複雑さに伴いは推奨されません。
* A4SWIFT セットアップが常に実行を`/InstallPlatform`引数。 結果として、セットアップは、msvcr71.dll、mfc71u.dll、msvcp71.dll および atl71.dll、Visual Studio の必要なを常にインストールされます。 これらの DLL ファイルをインストール、`%WINDIR%\System32`フォルダーかどうか、Dll は、か以前インストールされています。

### <a name="default-installation"></a>既定のインストール

1. 実行、 [!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe**管理者として。
2. **[インストール]** を選択します。
3. **[ユーザー名]**、**[組織]**、およびプロダクト キーを入力します。 **[次へ]** を選択します。
4. ライセンスの規約を確認し、 **Accept**します。
5. 選択**完了**、し、**次**します。
6. レビュー、**概要**ページ。 変更を加えるには、次のように選択します。**戻る**します。

    システム再起動後に自動的にログオンするには、**[設定]** を選択して、サインイン アカウントを入力します。 これは、セットアップ中にのみ有効です。 セットアップが完了すると、この設定は無効になります。

    **[インストール]** を選択します。

7. 選択**完了**を完了するとします。 ような一時フォルダーにセットアップ ログ ファイルを生成:`C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`します。

> [!NOTE]
> 場合**構成ウィザードの実行**がインストールの完了 ページで、選択されて、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザードをクリックすると、自動的に実行**完了**します。 


### <a name="custom-installation"></a>カスタム インストール

1. 実行、 [!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe**管理者として。
2. **[インストール]** を選択します。
3. **[ユーザー名]**、**[組織]**、およびプロダクト キーを入力します。 **[次へ]** を選択します。
4. ライセンスの規約を確認し、 **Accept**します。
5. 選択**カスタム**、し、**次**します。
6. コンポーネントを選択し、選択**次**:


   |                     選択するオプション                      |                                                                      目的                                                                      |
   |------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                  A4Swift のコンポーネント                  |                          BizTalk Server と SWIFT のメッセージの処理 (スキーマの解決、解析、検証) するために必要                          |
   |          メッセージの修復と調整           |    パイプライン、オーケストレーション、および実行時のスキーマをインストールします。 メッセージング、修復、および調整には、SQL Server で、A4SWIFT データベースを作成します。     |
   | メッセージ repair and new submission の web コンポーネント | Message Repair and New Submission の検証、証明書のセキュリティ、履歴、および BIC 参照用の web サービスを作成するには、コンポーネントをインストールします。 |
   |            ソフトウェア開発キット (SDK)            |                                    Visual Studio のサンプル ソース コード、ツールキット、およびスターター プロジェクトが含まれています。                                    |
   |                BRE 配置ユーティリティ                |               既に展開されている SWIFT のメッセージの種類に関連付ける、ビジネス ルール エンジン (BRE) ポリシーを配置するためのユーティリティ。               |
   |                       チュートリアル                       |                                Iincludes 指示と BizTalk Server で SWIFT ソリューションを開発するためのサンプルです。                                 |
   |                        ツール                         |                                                       A4SWIFT の開発用ツールが含まれています。                                                        |
   |                        Source                        |                                                 A4SWIFT の開発用のソース コードのサンプルをインストールします。                                                 |


7. レビュー、**概要**ページ。 変更を加えるには、次のように選択します。**戻る**します。

    **[インストール]** を選択します。

8. 選択**完了**を完了するとします。 ような一時フォルダーにセットアップ ログ ファイルを生成:`C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`します。

> [!NOTE]
> 場合**構成ウィザードの実行**がインストールの完了 ページで、選択されて、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザードをクリックすると、自動的に実行**完了**します。 

## <a name="next-steps"></a>次の手順
[BizTalk Accelerator for SWIFT に構成します。 ](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)