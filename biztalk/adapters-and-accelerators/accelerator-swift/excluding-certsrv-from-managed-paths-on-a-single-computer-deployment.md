---
title: "1 台のコンピューター展開上のパスを管理から CertSrv を除く |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed paths
- certificate server (CertSrv)
- certificates, certificate server (CertSrv)
ms.assetid: 39916663-b80e-49d8-ba9b-49276eb564fc
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c77fc1733859cd903bafcebc26162323feff82d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="excluding-certsrv-from-managed-paths-on-a-single-computer-deployment"></a>1 台のコンピューター展開の管理パスから CertSrv の除外
展開した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]1 台のコンピューターにも証明書サーバーをインストールし、同じコンピューター上での管理パスから証明書サーバー (CertSrv) を除外する必要があります。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] SharePoint サーバーのサーバーの全体管理。  
  
### <a name="to-exclude-certsrv-from-the-managed-paths"></a>管理パスから CertSrv を除外するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**SharePoint サーバーの全体管理**です。  
  
2.  ウィンドウで、サーバーの全体管理で、**仮想サーバーの構成**セクションで、**仮想サーバーの設定を構成する**です。  
  
3.  仮想サーバーの一覧] ウィンドウで、[ **Default Web Site**です。  
  
4.  仮想サーバーの設定] ウィンドウで、**仮想サーバーの管理**セクションで、[**管理パスの定義**です。  
  
5.  管理パスの定義] ウィンドウで、[、**新しいパスを追加**セクションで、入力**CertSrv**で、**パス**テキスト ボックス。 **型**セクションで、**エクスクルード パス**です。 **[OK]**をクリックします。  
  
6.  管理パスの定義ウィンドウを閉じます。