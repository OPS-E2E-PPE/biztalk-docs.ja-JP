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
ms.openlocfilehash: f5c431b90d1d128831f18d2ec1f53acfc891d91d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336920"
---
# <a name="how-to-install-the-sso-administration-component"></a>SSO 管理コンポーネントをインストールする方法

## <a name="overview"></a>概要
スタンドアロン機能としては、エンタープライズ シングル サインオンの管理コンポーネントをインストールすることができます。 これは、SSO システムをリモートで管理する必要がある場合に便利です。 ハードウェアおよびソフトウェア要件は、一般的なエンタープライズ SSO ランタイム サービスのインストールの場合と同様です。  
  
 管理コンポーネントをインストールした後は、管理のために使用する SSO サーバーを入力します。 コマンド ライン ツール (ssomanage.exe) または SSO 管理 MMC スナップインで、これを行うことができます。 どちらの手順は、このトピックに表示されます。  
  
 SSO 管理ユーティリティ (ssomanage.exe) をインストールしても、コマンド ライン ユーティリティへのアクセスには、[スタート] メニューのショートカットは作成されません。 インストール後に、SSO 管理ユーティリティを実行するには必要があります、コマンド プロンプトを開きし、ある SSO ディレクトリに移動します`Program Files\Common Files\Enterprise Single Sign-On`します。  
  
 エンタープライズ SSO 管理機能は、MMC スナップインも含まれます。 MMC 3.0 は、関数にスナップインのコンピューターにインストールする必要があります。  
  
 エンタープライズ SSO MMC スナップインを開く、**開始**メニューの **すべてのプログラム**を選択します**Microsoft エンタープライズ シングル サインオン**、し**SSO管理**します。  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a>エンタープライズ シングル サインオン管理コンポーネントをインストールします。  
  
- カスタム インストール実行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、エンタープライズ シングル サインオン管理機能のみを選択します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、下に表示されますこの**追加ソフトウェア**します。  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a>MMC スナップインを使用してサーバーを入力します。  
  
1.  場所が現在インストールされていないコンピューターで管理コンポーネントをインストールした後、SSO 管理スナップインを開きます。  
  
     **開始**メニューの **すべてのプログラム**を選択します**Microsoft エンタープライズ シングル サインオン**、し、 **SSO 管理**します。  
  
2.  MMC スナップインで、**コンソール ルート**を右クリックして**エンタープライズ シングル サインオン**、 をクリック**選択**します。  
  
     **SSO サーバーの選択** ダイアログ ボックスが表示されます。  
  
3.  入力するかを指定する SSO サーバー名を参照します。 コンピューターのすべてのユーザーの SSO サーバーを指定する**すべてのユーザーの SSO サーバーを設定**します。  
  
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
