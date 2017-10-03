---
title: "BizTalk Server 2016 のインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f5ac913-0734-45b2-8e25-1db146d81858
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f89aa7599040a2cc6c50f11b70c2751fcf2df1ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-server-2016"></a>BizTalk Server 2016 のインストール
BizTalk Server を単一のサーバーにインストールします。

## <a name="before-you-get-started"></a>始める前に

* **システム管理者** – SQL Server をインストールすると、セットアップによりサインイン アカウントにシステム管理者権限が自動的に付与されます。 BizTalk Server のインストールにもこれらの権限が必要なため、次のいずれかを実行します。
  * SQL Server のインストール時に使用した同じアカウントを使用する。
  * サインイン アカウントにシステム管理者の権限を付与する。
  * サインイン アカウントがローカルの Administrators グループのメンバーであることを確認する。
* **アカウント名** – 可能な場合は常に既定のアカウント名を使用してください。 BizTalk Server のセットアップでは自動的に既定のアカウントが入力されます。 ドメイン内に複数の BizTalk Server グループがある場合は、競合を防ぐためアカウント名を変更してください。 名前を変更する場合は、BizTalk Server では、サービス アカウントおよび Windows グループに対しては *<NetBIOS ドメイン名>\<ユーザー>* だけがサポートされます。
* **アカウント名と BAM 管理 Web サービス**: BizTalk Server では、ビルトイン アカウントまたはパスワードなしのアカウントを BAM 管理 Web サービス ユーザーに使用することはサポートされていません。 Web サービスが BizTalk Server データベースにアクセスする際、これらのアカウントでセキュリティの脅威が生じる場合があります。

    > [!NOTE] 
    > これらの種類のアカウントで BizTalk Server を構成すると成功する場合がありますが、BAM 管理 Web サービスは失敗します。 ビルトイン アカウントまたはパスワードなしのアカウントは、BAM アプリケーション プールに使用できます。

* **BizTalk アセンブリ ビューアー** – 64 ビットのプラットフォームではサポートされません。 
* **インストールとアンインストール** – BizTalk Server をアンインストールするには、手動で BizTalk Server データベースを削除する必要があります。 BizTalk Server を開発者または評価担当者としてインストールする場合は、仮想マシンを使用します。 再インストールが必要になった場合は、アンインストールやデータベースを削除することなく、仮想コンピューターを簡単にロールバックできます。
* **32 ビットおよび 64 ビットのコンピューター** – 32 ビットまたは 64ビットのコンピューターへの BizTalk Server のインストールに大きな違いはありません。 インストールと構成は 32 ビットおよび 64 ビットのコンピューターに対応しています。 特に違いはありません。
* **ワークグループ** - 単一コンピューター上のワークグループ環境に BizTalk Server をインストールして構成できます。 SQL Server と BizTalk Server の機能とコンポーネントは、同じコンピューターにインストールされて構成されます。


## <a name="install-biztalk-server"></a>BizTalk Server のインストール
1. 開いているプログラムをすべて閉じます。 BizTalk Server のセットアップを管理者として実行します。
2. **[Microsoft BizTalk Server 2016 のインストール]** を選択します。
3. **[ユーザー名]**、**[組織]**、およびプロダクト キーを入力します。 **[次へ]** を選択します。
4. ライセンス契約に同意して、**[次へ]** を選択します。
5. カスタマー エクスペリエンス向上プログラムへの参加を選択し、**[次へ]** を選択します。
6. インストールするコンポーネントを選択します。

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    必ず **[追加ソフトウェア]** を選択してください。 インストール場所を変更することもできます。 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    **[次へ]** を選択します。   
  
 7. 選択したコンポーネントによっては、追加の前提条件がある場合があります (ADOMD.NET など)。 セットアップは、再配布可能なすべての前提条件を自動的にインストールできます。 次のような方法があります。
* **[必要な再配布可能コンポーネントを手動でインストールする]**: インストール ウィザードが閉じ、不足しているコンポーネントを手動でインストールできます。
* **[必要な再配布可能コンポーネントを Web から自動的にインストールする]**: 既定の設定です。 インターネットへのアクセスが必要です。
* **[必要な再配付可能コンポーネントの CAB ファイルをダウンロードする]**: CAB ファイルをダウンロードして後でインストールします。
* **[必要な再配布可能コンポーネントを CAB ファイルから自動的にインストールする]**: 前に CAB ファイルをダウンロードしてある場合、このオプションを選択してその CAB ファイルを使用できます。 

  **[次へ]** を選択します。
  
8. 概要ページを確認します。 変更する場合は、**[戻る]** を選択してコンポーネントをオンまたはオフにします。 

     システム再起動後に自動的にログオンするには、**[設定]** を選択して、サインイン アカウントを入力します。 これは、BizTalk のセットアップ中にのみ可能です。 セットアップが完了すると、この設定は無効になります。 

    **[インストール]** を選択します。
  
9. BizTalk をすぐに構成するには、**[BizTalk Server 構成の開始]** をオンにします。 BizTalk をすぐに構成しない場合は、このオプションをオフにし、**[完了]** を選択してインストール ウィザードを終了します。 

セットアップ ログ ファイルが `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm` などの一時フォルダーに生成されます。
  
## <a name="check-the-installation"></a>インストールを確認する

* BizTalk Server が **[プログラムと機能]** の一覧に表示されます。
* レジストリ キー `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0` に、BizTalk Server のバージョン、インストール パス、エディション、その他の詳細が列記されます。
* BizTalk Server の管理、構成、その他のコンポーネントが、アプリの一覧に表示されます。 

## <a name="next-step"></a>次の手順
[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)