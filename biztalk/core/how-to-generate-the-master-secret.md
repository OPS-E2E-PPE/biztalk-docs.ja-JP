---
title: "マスター シークレットを生成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, generating
- managing [Master Secret server], generating
ms.assetid: 5512a8ee-bc5b-4fe4-90c7-41e3baaa723b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfbe186aee99616fa35e8f1e98f67c6ac75593c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-generate-the-master-secret"></a>マスター シークレットを生成する方法
この作業を実行するには、マスター シークレット サーバーに対する管理者権限が必要です。 また、この作業はマスター シークレット サーバーから実行する必要があります。  
  
 最初にエンタープライズ シングル サインオンをインストールしたサーバーが、マスター シークレット サーバーになります。  
  
> [!IMPORTANT]
>  SSO システムに配置できるマスター シークレット サーバーは 1 台のみです。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール実行時にエンタープライズ シングル サインオンをインストールすると、マスター シークレットは構成ウィザードの手順の一部として生成されます。 この作業は、新しいマスター シークレットを生成する場合にのみ行う必要があります。  
  
### <a name="to-generate-the-master-secret-using-the-mmc-snap-in"></a>MMC スナップインを使用してマスター シークレットを生成するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**シークレットの生成**です。  
  
### <a name="to-generate-the-master-secret-using-the-command-line"></a>コマンド ラインを使用してマスター シークレットを生成するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssoconfig – generateSecret \<*バックアップ ファイル*>**ここで、 \<*バックアップ ファイル*> をマスター シークレットを含むファイルの名前を指定します。  
  
     作成したファイルを保護するためのパスワードを入力するように求められます。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)   
 [マスター シークレット サーバー](../core/master-secret-server.md)   
 [マスタ シークレットの管理](../core/managing-the-master-secret.md)