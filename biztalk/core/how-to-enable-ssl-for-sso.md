---
title: "SSO の SSL を有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, SSL
- managing [SSO], enabling SSL
- SSL
ms.assetid: 0d75962a-a0b0-4e69-8001-54e7df617006
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ae2f3840cd2620f9c03a5b207b32d8bbd4feee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-ssl-for-sso"></a>SSO の SSL を有効にする方法
このコマンドを使用すると、すべてのエンタープライズ シングル サインオン (SSO) サーバーと SSO データベース間で Secure Sockets Layer (SSL) を有効にすることができます。  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンで SSL を有効にするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoconfig – setSSL\<はい/いいえ >**ここで、 \<**はい/いいえ**> SSO システムで SSL を有効にするかどうかを示します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO の使用](../core/using-sso.md)