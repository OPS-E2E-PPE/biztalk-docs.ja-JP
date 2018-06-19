---
title: 関連アプリケーションを削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec290d38-0220-4bf2-b596-2d6453e51c8d
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: d0632f7e4217cb9bbccd2ee604688f22eb6de348
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250982"
---
# <a name="how-to-delete-an-affiliate-application"></a>関連アプリケーションを削除する方法
MMC スナップインを使用して、または**deleteapps**資格情報データベースから指定された関連アプリケーションを削除するコマンド。  
  
> [!IMPORTANT]
>  関連アプリケーションを削除すると、そのアプリケーションに関連付けられたすべてのマッピングが自動的に削除されます。  
  
> [!IMPORTANT]
>  この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a>MMC スナップインを使用して関連アプリケーションを削除するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。  
  
2.  MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  関連アプリケーションを右クリックし、をクリックし、 **削除**します。  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a>コマンド ラインを使用して関連アプリケーションを削除するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –deleteapp <application name>`ここで、 *\<アプリケーション名 >* 資格情報データベースから削除する関連アプリケーションの名前を指定します。  
  
## <a name="see-also"></a>参照  
 [SSO 関連アプリケーション](../esso/sso-affiliate-applications.md)   
 [関連アプリケーションを有効にする方法](../esso/how-to-enable-an-affiliate-application.md)   
 [ユーザー マッピングを管理します。](../esso/managing-user-mappings.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)