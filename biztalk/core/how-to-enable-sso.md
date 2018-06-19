---
title: SSO を有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], creating
- SSO, enabling
- maps [SSO], creating
- managing [SSO], enabling
- SSO, maps
- SSO, applications
- creating, applications [SSO]
- managing [SSO], creating affiliate applications
ms.assetid: dda89d15-6b70-4c40-b658-2f6cbdd545c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a843c0f6cdea32ba5218140069163058fcd42442
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25970410"
---
# <a name="how-to-enable-sso"></a>SSO を有効にする方法
MMC スナップインまたはコマンド ラインを使用して、エンタープライズ シングル サインオン (SSO) システムを全面的に有効にすることができます。  
  
 有効化コマンドを実行した後、各シングル サインオン サーバーで最新のグローバル情報を取得するために SSO データベースをポーリングするので、すべてのサーバーが有効になるまでに、若干の遅延が発生します。  
  
 SSO システムの関連アプリケーションおよびマッピングを構成する場合、関連アプリケーションを作成する必要もあります。 SSO 関連管理者が関連アプリケーションを作成した後で、アプリケーション管理者が変更を加えたり、アプリケーション ユーザー (エンド ユーザー) が自分のマッピングを作成したりできます。 詳細については、次を参照してください。[関連アプリケーションを管理する](../core/managing-affiliate-applications.md)と[ユーザー マッピングを管理する](../core/managing-user-mappings.md)です。  
  
### <a name="to-enable-the-sso-system-using-the-mmc-snap-in"></a>MMC スナップインを使用して SSO システムを有効にするには  
  
1.  をクリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  右クリック **システム**, 、クリックして **を有効にする**です。  
  
### <a name="to-enable-the-sso-system-using-the-command-line"></a>コマンド ラインを使用して SSO システムを有効にするには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssomanage – enablesso**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-enable-sso-to-create-affiliate-applications-and-mappings"></a>SSO で関連アプリケーションおよびマッピングを作成できるようにするには  
  
1.  SSO 管理者または SSO 関連管理者として、SSO サーバーか、SSO の SSO 管理サブサービスを実装しているコンピューターにログオンします。  
  
2.  **開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
3.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
4.  型 **ssomanage-enablesso** エンタープライズ シングル サインオン サービスを有効にします。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
5.  SSO 関連管理者としてログオンします。  
  
6.  型**ssomanage - createapps」と入力*\<アプリケーション ファイル\>*** 関連アプリケーションを作成する場所\<アプリケーション ファイル\>XML ファイルです関連アプリケーションの定義が含まれています。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO サーバーを設定する方法](../core/how-to-set-the-sso-server.md)   
 [SSO を無効にする方法](../core/how-to-disable-sso.md)   
 [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)   
 [SSO の使用](../core/using-sso.md)