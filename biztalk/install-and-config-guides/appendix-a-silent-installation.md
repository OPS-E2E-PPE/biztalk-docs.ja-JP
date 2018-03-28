---
title: '付録 a: サイレント インストール |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94ded6b3-13ca-47e6-a038-254514f500e7
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03568f86b8c3b609fed74a9faf7f6057614151c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="appendix-a-silent-installation"></a>付録 A: サイレント インストール
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のサイレント インストールの作成手順を示します。  
  
## <a name="create-a-silent-installation"></a>サイレントインストールの作成  
  
1.  **[スタート]** ボタンをクリックし、**[すべてのプログラム]**、**[アクセサリ]**、**[コマンド プロンプト]** の順にクリックします。  
  
2.  インストール場所に移動します。 コマンド プロンプトで「`setup.exe /``<command name> <options>`」と入力し、**Enter** キーを押します。 ログ ファイルにインストール状況が表示されます。  
  
|コマンド名|オプション|Description|  
|------------------|------------|-----------------|  
|/HELP、/?、または /H||ヘルプおよびクイック リファレンスを表示します。|  
|/QUIET||セットアップ実行中のユーザー インターフェイス (すべてのダイアログ ボックス、エラー、ユーザー入力を求めるプロンプト) の表示を抑制します。 メッセージはすべて、セットアップ ログ ファイルに記録されます。 **注:** /QUIET フラグは、アップグレードのときは指定できません。アップグレードの場合は、選択されたオプションをユーザーが確認する必要があるからです。|  
|/CABPATH|\<*CAB ファイルの場所*\>|再配布可能な CAB ファイルの場所を指定します。|  
|/S|\<*構成 XML ファイル*\>|この構成ファイルの中で指定されている機能のサイレント インストールが実行されます。 **注:** すべての機能をインストールするには、構成 XML ファイルの `InstalledFeature` パラメータに ALL を指定します。|  
|/PASSIVE||パッシブ インストールを実行します。 セットアップ プログラムは、進行状況バーのみを表示します。|  
|/NORESTART||再起動プロンプトを表示せずに、インストール終了時に自動的に再起動します。|  
|/FORCERESTART||インストール完了後、強制的に再起動します。|  
|/PROMPTRESTART||再起動する前に、ユーザーに確認を求めます。|  
|/X または /UNINSTALL||[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をアンインストールします。|  
|/L|\<Logfile\> [i] [w] [e] [a] [r] [u] [c] [m] [p] [v] [*]|指定したパスのログ ファイルに情報を書き込みます。 Windows インストーラーのログ記録モードは必ず "詳細" となります。また、既存のファイルに情報が追加されます。<br /><br /> ログに記録される情報を指定するフラグは、次のとおりです。<br /><br /> i - 状態を示すメッセージ<br /><br /> w - 致命的でない警告<br /><br /> e - すべてのエラー メッセージ<br /><br /> a - アクションの起動<br /><br /> r - アクション固有の記録<br /><br /> u - ユーザーの要求<br /><br /> c - 初期のユーザー インターフェイス パラメーター<br /><br /> m - メモリ不足<br /><br /> p - ターミナル プロパティ<br /><br /> v - 詳細出力<br /><br /> * - すべて|  
|/IGNOREDEPENDENCIES||ダウンロード可能な必要コンポーネントのチェックをバイパスします。|  
|/INSTALLDIR \<*インストール パス*\>|\<*プログラム ファイル フォルダー\>*|製品のインストール場所の完全パスを指定します。|  
|/COMPANYNAME|\<*会社名*\>|会社名または組織名を設定します。|  
|/USERNAME|\<*ユーザー名*\>|ユーザー名を設定します。|  
|/ADDLOCAL ALL||すべての機能をインストールします。 ADDLOCAL コマンドの詳細については、「[ADDLOCAL コマンドの値の一覧](http://go.microsoft.com/fwlink/p/?LinkID=189319)」をご覧ください。|  
|/REMOVE ALL||すべての機能を削除します。|  
|/REPAIR ALL||すべての機能を修復します。|  
|/CEIP||カスタマー エクスペリエンス向上プログラム (CEIP) を有効にします。|  
|/PRODUCT UDDI||UDDI をインストールします。|  
|msiexec.exe /i  [MSIPATH] INSTALLDIR=[INSTALLDIRPATH] DATADIR=[DATADIRPATH] SQLSERVERMACHINENAME=[SQLSERVERNAME] OVERWRITERFIDSTORE=1 INSTALLLEVEL=5 /lvxp RfidServicesInstall.txt /q<br /><br /> 例: msiexec.exe /i "\\\ABC\XYZ\RFID_x86\RfidServices.msi" INSTALLDIR=“C:\Program Files\Microsoft BizTalk RFID\” DATADIR=“C:\Program Files\Microsoft BizTalk RFID\” SQLSERVERMACHINENAME=(local) OVERWRITERFIDSTORE=1 INSTALLLEVEL=5 /lvxp RfidServicesInstall.txt /q||Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] RFID をインストールします。|  
  
 **追加情報**  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、電子的なソフトウェア配布の自動化 (サイレント インストール) が有効になっています。 サイレント インストールでは以下が実行されます:  
  
    -   同じ構成を持つコンピューターに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールします。  
  
    -   システム管理者は、ユーザーの操作なしに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をリモート コンピューターにインストールできます。  
  
    -   ユーザーはインストールを監視したり、入力したりする必要はありません。  
  
-   サイレント インストールを作成するには、コマンドライン オプションを使用してすべての操作を抑制します。  
  
-   サイレント インストールの完了後、コマンド ウィンドウには何も表示されません。 ステータスを確認するには、インストール ログ ファイルを使用します。  
  
