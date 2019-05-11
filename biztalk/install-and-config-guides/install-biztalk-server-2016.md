---
title: BizTalk Server 2016 のインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f5ac913-0734-45b2-8e25-1db146d81858
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97ea71a309d5073f0c1a00adeff5a94ea62cb958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266221"
---
# <a name="install-biztalk-server-2016"></a>BizTalk Server 2016 をインストールします。
1 台のコンピューターで BizTalk Server をインストールします。

## <a name="before-you-get-started"></a>始める前に

* **システム管理者**– SQL Server をインストールすると、セットアップがシステム管理者の権限に自動的に、サインイン済みのアカウントに付与されます。 これらの権限は BizTalk Server をインストールする必要であるため、次のいずれかの操作を行います。
  * SQL Server をインストールしたときに使用した同じアカウントを使用します。
  * サインイン アカウントにシステム管理者の権限を与えます。
  * サインイン アカウントがローカルの administrators グループのメンバーであることを確認します。
* **アカウント名**– 可能な限り、既定のアカウント名を使用します。 BizTalk Server のセットアップでは、既定のアカウントが自動的に入力します。 ドメイン内の複数の BizTalk Server グループがある場合は、競合を回避するために、アカウント名を変更します。 名前を変更する場合は、BizTalk Server のみをサポート*NetBIOS ドメイン名 \ ユーザー*のサービス アカウントと Windows グループ。
* **アカウント名と BAM 管理 Web サービス**– BizTalk Server はサポートされませんビルトイン アカウントまたはパスワードなしのアカウントを BAM 管理 Web サービス ユーザーです。 BizTalk Server データベースを web サービスにアクセスし、これらのアカウントがセキュリティの脅威をお勧めします。

    > [!NOTE] 
    > これらの種類のアカウントを BizTalk Server の構成が成功しないが、BAM 管理 Web サービスが失敗します。 BAM アプリケーション プールのビルトイン アカウントまたはパスワードなしのアカウントを使用できます。

* **BizTalk アセンブリ ビューアー** – 64 ビット プラットフォームでサポートされていません。 
* **インストールし、アンインストール**– BizTalk Server のアンインストールでは、BizTalk Server データベースを手動で削除する必要があります。 開発者またはエバリュエーターとして BizTalk Server をインストールする場合は、仮想マシンを使用します。 再インストールする必要がある場合に簡単にロールバックできます仮想マシンをアンインストールし、データベースを削除する必要はありません。
* **32 ビットおよび 64 ビット コンピューター** – 32 ビットまたは 64 ビット コンピューターで BizTalk Server をインストールするときにいくつか違いがあります。 インストールと構成は、32 ビットおよび 64 ビット コンピューターをについて説明します。 相違点が記載されています。
* **ワークグループ**-をインストールして、1 台のコンピューター上のワークグループ環境での BizTalk Server の構成がサポートされています。 SQL Server と BizTalk Server の機能とコンポーネントがインストールされ、同じコンピューター上で構成します。


## <a name="install-biztalk-server"></a>BizTalk Server をインストールします。
1. 開いているプログラムを閉じます。 BizTalk Server のセットアップを管理者として実行します。
2. 選択**Microsoft BizTalk Server 2016 のインストール**します。
3. 入力、**ユーザー名**、**組織**、およびプロダクト キー。 **[次へ]** を選択します。
4. ライセンス条項に同意し、選択**次**します。
5. 顧客のエクスペリエンス向上プログラムに参加し、選択**次**します。
6. インストールするコンポーネントを選択します。

    ![bts2016install_components](../install-and-config-guides/media/bts2016install-components.gif)
  
    必ず選択**追加ソフトウェア**します。 インストール場所を変更することもできます。 
  
    ![bts2016install_additional](../install-and-config-guides/media/bts2016install-additional.gif)

    **[次へ]** を選択します。   
  
   7. 選択したコンポーネント、によっていくつか追加の前提条件、ADOMD.NET などがあります。 自動的に再配布可能なすべての前提条件をインストールできます。 次のような方法があります。
7. **再頒布可能パッケージの前提条件を手動でインストール**:前提条件を手動でインストールできるようにインストール ウィザードを閉じます。
8. **Web サイトから再頒布可能パッケージのコンポーネントを自動的にインストール**:既定値です。 インターネットへのアクセスが必要です。
9. **再頒布可能コンポーネントの CAB ファイルをダウンロード**:後でインストールすることができる CAB ファイルをダウンロードします。
10. **再頒布可能パッケージの必須コンポーネントを CAB ファイルから自動的にインストール**:以前に CAB ファイルをダウンロードした場合は、その CAB ファイルを使用するには、このオプションを選択できます。 

    **[次へ]** を選択します。
  
11. [概要] ページを確認します。 変更を加えるには、次のように選択します。**戻る**チェックまたはすべてのコンポーネントをオフにします。 

      自動ログオンをできるように、システムの再起動後、次のように選択します。**設定**、サインイン アカウントを入力します。 これは、BizTalk セットアップ中にのみ有効です。 セットアップが完了したら、この設定を無効にします。 

     **[インストール]** を選択します。
  
12. 確認すると、BizTalk を構成するには、 **BizTalk Server 構成**します。 BizTalk をすぐに構成しない場合は、このオプションをオフにし、選択**完了**インストール ウィザードを終了します。 

ような一時フォルダーには、セットアップ ログ ファイルが生成されます。 `C:\Users\*username*\AppData\Local\Setup(011217 xxxxxx).htm`
  
## <a name="check-the-installation"></a>インストールを確認します。

* BizTalk Server が記載**プログラムと機能**します。
* `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0`レジストリ キーには、BizTalk Server のバージョン、インストール パス、エディション、およびその他の詳細が一覧表示されます。
* BizTalk Server 管理、構成、およびその他のコンポーネントは、アプリに表示されます。 

## <a name="next-step"></a>次の手順
[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)