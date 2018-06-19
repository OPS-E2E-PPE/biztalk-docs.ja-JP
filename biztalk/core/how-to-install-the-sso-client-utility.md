---
title: SSO クライアント ユーティリティをインストールする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 4eba4e0747c9566c5303e04602d957173cc56052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254250"
---
# <a name="how-to-install-the-sso-client-utility"></a>SSO クライアント ユーティリティをインストールする方法
スタンドアロンの SSO クライアント ユーティリティ (コマンド ライン ユーティリティ ベースおよびユーザー インターフェイス ベース) を使用すると、エンド ユーザーが SSO データベースでクライアントのマッピングを構成できます。 クライアント ユーティリティは、SSO 管理機能と一緒にインストールされる自己展開型ファイル (SSOClientInstall.exe) からインストールできます。 管理者は、ネットワーク共有上にインストーラ パッケージのコピーを配置することで、クライアント ユーザーがインストーラ パッケージを使用できるようにすることもできます。  
  
 SSO クライアント ユーティリティをインストールするには、クライアント コンピュータで次のオペレーティング システムのいずれかを実行している必要があります。  
  
-   [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]  
  
-   [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] または [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] (UI ベースの SSO クライアント ユーティリティを使用する場合、またはエンタープライズ SSO の相互運用マネージ コンポーネントを利用する場合にのみ必要です)。  
  
 SSO クライアント ユーティリティをインストールした後を実行してから、**開始** をクリックしてメニュー**プログラム**、 **Microsoft エンタープライズ シングル サインオン**、し**SSO クライアント ユーティリティ**です。  
  
### <a name="to-install-the-sso-client-utility"></a>SSO クライアント ユーティリティをインストールするには  
  
1.  インストーラ パッケージ SSOClientInstall をダブルクリックします。  
  
    > [!NOTE]
    >  このファイルが企業内のどこにあるのかについては、エンタープライズ シングル サインオン管理者に問い合わせてください。  
  
     **WinZip Self-extractor**プログラムが表示されます。  
  
2.  ファイルを解凍し、をクリックする場所のフォルダーを選択**Unzip**です。  
  
     ファイルは一時フォルダに解凍することをお勧めします。  
  
     **エンタープライズ シングル サインオン クライアント セットアップ**プログラムが表示されます。  
  
3.  **エンタープライズ シングル サインオン クライアントへようこそ**  ページで、をクリックして**次**です。  
  
4.  使用許諾契約書 ページで、をクリックして**本ライセンス契約の条項に同意**、順にクリック**次**です。  
  
5.  **ユーザー情報** ページで、ユーザー名、組織名を入力してをクリックして**次**です。  
  
6.  **インストールの開始**] ページで [**インストール**です。  
  
7.  **エンタープライズ シングル サインオン クライアント ウィザードの完了**] ページで [**完了**です。  
  
8.  次のいずれかの手順を実行し、SSO サーバーを指定します。  
  
    -   ENTSSO 管理の MMC スナップインを開きます。 **SSO サーバーの選択**ダイアログが表示されます。 管理操作の実行時に接続する SSO サーバーについて、名前を入力するか、または参照します。 コンピューター上のすべてのユーザーの SSO サーバーを指定するには、選択**すべてのユーザーの SSO サーバーの設定**です。  
  
         または  
  
    -   コマンド プロンプトで「`ssomanage –server`を目的の SSO サーバーを指定します。 入力することも`ssomanage -serverall`管理操作を実行するときに、このコンピューターのすべてのユーザーが接続する SSO サーバーを指定します。  
  
## <a name="see-also"></a>参照  
 [SSO 管理コンポーネントをインストールする方法](../core/how-to-install-the-sso-administration-component.md)   
 [SSO を構成します。](../core/configuring-sso.md)   
 [SSO のインストール](../core/installing-sso.md)