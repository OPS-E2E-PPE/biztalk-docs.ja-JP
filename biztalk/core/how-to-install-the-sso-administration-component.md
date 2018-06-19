---
title: SSO 管理コンポーネントのインストール |Microsoft ドキュメント
description: SSO の管理を取得するカスタム インストールを実行して、ssomanage または SSO 管理を使用して、BizTalk Server でサーバー名を入力するには
ms.custom: ''
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 096839e2-7129-498d-92ee-5afeea8dbe0d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2bb01defe700408a551a144eae67d0405565f4
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2017
ms.locfileid: "22317987"
---
# <a name="how-to-install-the-sso-administration-component"></a>SSO 管理コンポーネントをインストールする方法

## <a name="overview"></a>概要
スタンドアロン機能として、エンタープライズ シングル サインオンの管理コンポーネントをインストールすることができます。 このコンポーネントは、SSO システムをリモートで管理する必要がある場合に便利です。 ハードウェアおよびソフトウェアの要件は、一般的なエンタープライズ SSO ランタイム サービスのインストールと同じです。  
  
 管理コンポーネントをインストールした後は、管理用に使用する SSO サーバーを入力します。 コマンド ライン ツール (ssomanage.exe) または SSO 管理 MMC スナップインで、これを行うことができます。 どちらの手順は、このトピックに記載されています。  
  
 SSO 管理ユーティリティ (ssomanage.exe) をインストールしても、コマンド ライン ユーティリティにアクセスするショートカットは [スタート] メニューに作成されません。 をインストールした後、SSO 管理ユーティリティを実行するには、コマンド プロンプトを開き、とにある SSO ディレクトリに移動する必要があります`Program Files\Common Files\Enterprise Single Sign-On`です。  
  
 エンタープライズ SSO の管理機能には、MMC スナップインも含まれています。 MMC 3.0 は、関数にスナップインのコンピューターにインストールする必要があります。  
  
 開くには、エンタープライズ SSO MMC スナップインから、**開始**メニューの **すべてのプログラム** **Microsoft エンタープライズ シングル サインオン**、し**SSO管理**です。  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a>エンタープライズ シングル サインオン管理コンポーネントをインストールします。  
  
-   カスタム インストールを行う[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、エンタープライズ シングル サインオン管理機能のみを選択します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、下に記載されてこの**追加のソフトウェア**です。  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a>MMC スナップインを使用してサーバー名を入力します。  
  
1.  現在管理コンポーネントがインストールされていないコンピューターに管理コンポーネントをインストールした後、SSO 管理スナップインを開きます。  
  
     **開始**メニューの **すべてのプログラム** **Microsoft エンタープライズ シングル サインオン**、し、 **SSO 管理**です。  
  
2.  MMC スナップインで、**コンソール ルート**を右クリックして**エンタープライズ シングル サインオン**、 をクリック**選択**です。  
  
     **SSO サーバーの選択** ダイアログ ボックスが表示されます。  
  
3.  指定する SSO サーバーの名前を入力または参照します。 コンピューター上のすべてのユーザーの SSO サーバーを指定するには、選択**すべてのユーザーの SSO サーバーの設定**です。  
  
4.  **[OK]** をクリックします。  
  
## <a name="enter-the-server-using-the-command-line-tool"></a>コマンド ライン ツールを使用してサーバー名を入力します。  
  
1.  をクリックして**開始**、 をクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは`\Program Files\Common Files\Enterprise Single Sign-On`します。  
  
3.  次のオプションのいずれかを選択して、SSO サーバーを入力します。  
  
    1.  型**ssomanage – server**管理操作を実行するときに接続する SSO サーバーを入力します。  
  
         \- または -  
  
    2.  型**ssomanage-serverall**管理操作を実行するときにこのコンピューターのすべてのユーザーが接続する SSO サーバーを入力します。  
  
## <a name="see-also"></a>参照  
 [SSO クライアント ユーティリティをインストールする方法](../core/how-to-install-the-sso-client-utility.md)   
 [SSO を構成します。](../core/configuring-sso.md)   
 [SSO のインストール](../core/installing-sso.md)
