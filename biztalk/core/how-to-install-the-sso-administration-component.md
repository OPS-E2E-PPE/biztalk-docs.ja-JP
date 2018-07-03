---
title: SSO 管理コンポーネントのインストール |Microsoft Docs
description: SSO の管理のためのカスタム インストールを行い、ssomanage または SSO 管理を使用して、BizTalk Server で、サーバー名を入力します。
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
ms.openlocfilehash: 3f510a876102ec867e2f2f16676cef63cedfaa92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981331"
---
# <a name="how-to-install-the-sso-administration-component"></a>SSO 管理コンポーネントをインストールする方法

## <a name="overview"></a>概要
スタンドアロン機能としては、エンタープライズ シングル サインオンの管理コンポーネントをインストールすることができます。 このコンポーネントは、SSO システムをリモートで管理する必要がある場合に便利です。 ハードウェアおよびソフトウェアの要件は、一般的なエンタープライズ SSO ランタイム サービスのインストールと同じです。  
  
 管理コンポーネントをインストールした後は、管理のために使用する SSO サーバーを入力します。 コマンド ライン ツール (ssomanage.exe) または SSO 管理 MMC スナップインで、これを行うことができます。 どちらの手順は、このトピックに表示されます。  
  
 SSO 管理ユーティリティ (ssomanage.exe) をインストールしても、コマンド ライン ユーティリティにアクセスするショートカットは [スタート] メニューに作成されません。 インストール後に、SSO 管理ユーティリティを実行するには必要があります、コマンド プロンプトを開きし、ある SSO ディレクトリに移動します`Program Files\Common Files\Enterprise Single Sign-On`します。  
  
 エンタープライズ SSO の管理機能には、MMC スナップインも含まれています。 MMC 3.0 は、関数にスナップインのコンピューターにインストールする必要があります。  
  
 エンタープライズ SSO MMC スナップインを開く、**開始**メニューの **すべてのプログラム**を選択します**Microsoft エンタープライズ シングル サインオン**、し**SSO管理**します。  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a>エンタープライズ シングル サインオン管理コンポーネントをインストールします。  
  
- カスタム インストール実行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、エンタープライズ シングル サインオン管理機能のみを選択します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、下に表示されますこの**追加ソフトウェア**します。  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a>MMC スナップインを使用してサーバーを入力します。  
  
1.  現在管理コンポーネントがインストールされていないコンピューターに管理コンポーネントをインストールした後、SSO 管理スナップインを開きます。  
  
     **開始**メニューの **すべてのプログラム**を選択します**Microsoft エンタープライズ シングル サインオン**、し、 **SSO 管理**します。  
  
2.  MMC スナップインで、**コンソール ルート**を右クリックして**エンタープライズ シングル サインオン**、 をクリック**選択**します。  
  
     **SSO サーバーの選択** ダイアログ ボックスが表示されます。  
  
3.  指定する SSO サーバーの名前を入力または参照します。 コンピューターのすべてのユーザーの SSO サーバーを指定する**すべてのユーザーの SSO サーバーを設定**します。  
  
4.  **[OK]** をクリックします。  
  
## <a name="enter-the-server-using-the-command-line-tool"></a>コマンド ライン ツールを使用してサーバーを入力します。  
  
1.  クリックして**開始**、 をクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは`\Program Files\Common Files\Enterprise Single Sign-On`します。  
  
3.  次のオプションのいずれかを選択して、SSO サーバーを入力します。  
  
    1.  型**ssomanage – server**管理操作を実行するときに接続する SSO サーバーを入力します。  
  
         \- または -  
  
    2.  型**ssomanage-serverall**管理操作を実行するときに、このコンピューターのすべてのユーザーが接続する SSO サーバーを入力します。  
  
## <a name="see-also"></a>参照  
 [SSO クライアント ユーティリティをインストールする方法](../core/how-to-install-the-sso-client-utility.md)   
 [SSO を構成します。](../core/configuring-sso.md)   
 [SSO のインストール](../core/installing-sso.md)
