---
title: ユーザー マッピングを無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c745dd-4d39-46e5-88bf-b803ae2e0a1b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 93694ed8a3238be51b255bcad79122169461d885
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250974"
---
# <a name="how-to-disable-a-user-mapping"></a>ユーザー マッピングを無効にする方法
指定したマッピングに関連付けられたすべての操作を無効にするときに、ユーザー マッピングを無効にすることができます。 ユーザー マッピングは、削除する前に無効にする必要があります。  
  
 ユーザー マッピングを無効にする場合は (D) として表示されます*\<ドメイン >\\< ユーザー名\>* ユーザー マッピングを一覧表示します。  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>管理ユーティリティを使用してユーザー マッピングを無効にするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型`cmd`、キーを押します**ENTER**です。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –disablemapping <domain>\<username><application name>`ここで、 *\<ドメイン >* は Windows ドメイン ユーザー アカウントを*\<ユーザー名 >* Windows ユーザー名が無効にするには、資格情報、および*\<アプリケーション名 >* ユーザー マッピングを削除する関連アプリケーションの名前を指定します。  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>クライアント ユーティリティを使用してユーザー マッピングを無効にするには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型`cmd`、キーを押します**ENTER**です。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssoclient –disablemapping <application name>`ここで、 *\<アプリケーション名 >* ユーザー マッピングを削除する関連アプリケーションの名前を指定します。  
  
## <a name="see-also"></a>参照  
 [SSO マッピング](../esso/sso-mappings.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)   
 [ユーザー マッピングの管理](../esso/managing-user-mappings.md)