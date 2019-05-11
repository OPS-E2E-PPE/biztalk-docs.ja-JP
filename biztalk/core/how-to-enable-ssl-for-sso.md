---
title: SSO の SSL を有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, SSL
- managing [SSO], enabling SSL
- SSL
ms.assetid: 0d75962a-a0b0-4e69-8001-54e7df617006
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8478f688dc504ba64690f6f7b8d2a0faa4b31feb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337930"
---
# <a name="how-to-enable-ssl-for-sso"></a>SSO の SSL を有効にする方法
すべてのエンタープライズ シングル サインオン (SSO) サーバーと SSO データベース間で Secure Sockets Layer (SSL) を有効にするのにには、このコマンドを使用します。  
  
### <a name="to-enable-ssl-for-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンの SSL を有効にするには  
  
1.  クリックして**開始**、 をクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssoconfig – setSSL\<はい/いいえ\>** ここで、 \<**はい/いいえ**\> SSO システムで SSL を有効にするかどうかを示します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO の使用](../core/using-sso.md)