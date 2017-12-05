---
title: "ハードウェアおよびソフトウェア要件の展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, hardware requirements
- deploying, software requirements
ms.assetid: 1dd9c4bb-b724-4195-8496-eff95cd1548a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e772c409533e5ef6e3fedd13e3db7acbfdc572c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="hardware-and-software-requirements-for-deployment"></a>ハードウェアおよびソフトウェア要件の展開
次の表は、ハードウェアとソフトウェアの推奨事項と要件の指定された展開アーキテクチャ内の各サーバーを一覧表示します。 必要なソフトウェアの構成に関する詳細については、「[サーバーの展開](../../adapters-and-accelerators/accelerator-swift/deploying-your-servers.md)です。  
  
 すべてのサーバーの種類のハード_ディスク空き容量、プロセッサのクロック速度、および現在および将来の技術的な要件に基づくランダム アクセス メモリ (RAM) の量を選択します (」の説明に従って[手順 1: 基本プラットフォームをインストールする](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)).  
  
|[サーバー]|ハードウェアの推奨事項|ソフトウェア要件|  
|------------|------------------------------|---------------------------|  
|ドメイン コント ローラー|-1 のネットワーク アダプター|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 または 2012<br />-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)]サーバー<br />ドメイン ネーム サーバー (DNS)|  
|Microsoft SQL server|2 つのネットワーク アダプター<br />-省略可能: 記憶域エリア ネットワーク (SAN) ディスクの選択の平均スループット、ピーク時のスループット、およびピーク時のスループット時間プラスに必要なハード_ディスク空き容量の平均メッセージ サイズ。 SAN は、3 つのドライブにパーティション分割する必要があります。 データ、トランザクション ログ、およびクォーラムです。|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 または 2012<br />-   [!INCLUDE[SQLServer2008or2005](../../includes/sqlserver2008or2005-md.md)]|  
|BizTalk サーバー メッセージング|2 つのネットワーク アダプター|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 または 2012<br />BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|  
|BizTalk HTTP フロント エンド サーバー (MRSR サイト)|2 つのネットワーク アダプター|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 または 2012<br />-インターネット インフォメーション サービス (IIS)<br />ルーティングが有効なメッセージ キュー サービス<br />BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|  
|オーケストレーションの BizTalk サーバー|-1 のネットワーク アダプター|-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2012 R2 または 2012<br />BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]|