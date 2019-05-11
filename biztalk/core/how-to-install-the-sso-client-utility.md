---
title: SSO クライアント ユーティリティをインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, client utility
- client utility [SSO]
- SSO, installing
ms.assetid: e14d257e-2fde-46af-b90c-5dbc0884536b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc7970f397c8b5c076edd7bf0f29e3d7cf8becd3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384916"
---
# <a name="how-to-install-the-sso-client-utility"></a>SSO クライアント ユーティリティをインストールする方法
スタンドアロンの SSO クライアント ユーティリティ (コマンド ライン ユーティリティとユーザー インターフェイスに基づく) は、エンドユーザーが SSO データベース内のクライアントのマッピングの構成に使用できます。 クライアント ユーティリティは、SSO 管理機能と共にインストールされる自己解凍形式のファイル (SSOClientInstall.exe) からインストールできます。 管理者は、ネットワーク共有上にインストーラ パッケージのコピーを配置することで、クライアント ユーザーがインストーラ パッケージを使用できるようにすることもできます。  
  
 SSO クライアント ユーティリティをインストールするには、クライアント コンピュータで次のオペレーティング システムのいずれかを実行している必要があります。  
  
- [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
- [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] または [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (UI ベースの SSO クライアント ユーティリティを使用する場合、またはエンタープライズ SSO の相互運用マネージド コンポーネントを利用する場合にのみ必要です)。  
  
  SSO クライアント ユーティリティをインストールした後からを起動できる、**開始**メニューをクリックして**プログラム**、 **Microsoft エンタープライズ シングル サインオン**、し**SSO クライアント ユーティリティ**します。  
  
### <a name="to-install-the-sso-client-utility"></a>SSO クライアント ユーティリティをインストールするには  
  
1.  インストーラ パッケージ SSOClientInstall をダブルクリックします。  
  
    > [!NOTE]
    >  企業では、このファイルの場所のエンタープライズ シングル サインオン管理者を確認します。  
  
     **WinZip Self-extractor**プログラムが表示されます。  
  
2.  フォルダー、ファイルを解凍し、をクリックして選択します**Unzip**します。  
  
     一時フォルダーにファイルを解凍することをお勧めします。  
  
     **エンタープライズ シングル サインオン クライアント セットアップ**プログラムが表示されます。  
  
3.  **エンタープライズ シングル サインオン クライアントへようこそ**  ページで **次**します。  
  
4.  使用許諾契約書 ページで、次のようにクリックします。**本ライセンス契約の条項に同意**、 をクリックし、**次**。  
  
5.  **ユーザー情報** ページで、ユーザー名、組織の名前を入力してをクリックし、**次**します。  
  
6.  **インストールの開始**] ページで [**インストール**します。  
  
7.  **エンタープライズ シングル サインオン クライアント ウィザードの完了**] ページで [**完了**します。  
  
8.  次のいずれかの手順を実行して、SSO サーバーを指定します。  
  
    -   ENTSSO 管理 MMC スナップインを開きます。 **SSO サーバーの選択**ダイアログが表示されます。 入力するか、管理操作を実行するときに接続する SSO サーバーを参照します。 コンピューターのすべてのユーザーの SSO サーバーを指定する**すべてのユーザーの SSO サーバーを設定**します。  
  
         スイッチまたは  
  
    -   コマンド プロンプトで「`ssomanage –server`目的の SSO サーバーを指定します。 入力することも`ssomanage -serverall`管理操作を実行するときにこのコンピューターのすべてのユーザーが接続する SSO サーバーを指定します。  
  
## <a name="see-also"></a>参照  
 [SSO 管理コンポーネントをインストールする方法](../core/how-to-install-the-sso-administration-component.md)   
 [SSO を構成します。](../core/configuring-sso.md)   
 [SSO のインストール](../core/installing-sso.md)