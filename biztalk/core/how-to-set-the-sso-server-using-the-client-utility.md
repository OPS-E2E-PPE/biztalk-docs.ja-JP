---
title: クライアント ユーティリティを使用して SSO サーバーを設定する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], selecting servers
- managing [SSO applications], selecting servers
- SSOClient [SSO], selecting servers
ms.assetid: a0f1038c-60c9-4e9d-a730-1ecfa036743b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49b2145320bd8e22b01d312d62246fa282fb534e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-set-the-sso-server-using-the-client-utility"></a>クライアント ユーティリティを使用して SSO サーバーを設定する方法
ssoclient を使用するたびに、まず、ユーザーが構成情報を含む正しいシングル サインオン サーバーを参照するように設定する必要があります。  
  
### <a name="to-set-the-sso-server-for-a-user-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザーに対して SSO サーバーを設定するには  
  
1.  **開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssoclient – server *\<シングル サインオン サーバー\>* * *、どこで\<*シングル サインオン サーバー\>* でのシングル サインオン サーバーの名前を指定します、ユーザーに接続しようとします。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)