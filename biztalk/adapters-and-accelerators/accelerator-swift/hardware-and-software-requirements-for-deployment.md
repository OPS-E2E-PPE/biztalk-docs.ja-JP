---
title: ハードウェアおよびソフトウェアの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, hardware requirements
- deploying, software requirements
ms.assetid: 1dd9c4bb-b724-4195-8496-eff95cd1548a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f61a8b66f455aeffee1b5416ebb5911be61fdbec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984659"
---
# <a name="hardware-and-software-requirements-for-deployment"></a>ハードウェアとソフトウェアの展開要件
次の表は、ハードウェアとソフトウェアの推奨事項と規定されたデプロイ アーキテクチャ内の各サーバーの要件を示します。 必要なソフトウェアの構成の詳細については、次を参照してください。[サーバーの展開](../../adapters-and-accelerators/accelerator-swift/deploying-your-servers.md)します。  

 すべてのサーバーの種類のハード_ディスク空き容量、プロセッサのクロック速度、および現在と予想される技術的な要件に基づいてランダム アクセス メモリ (RAM) の量を選択します (」の説明に従って[手順 1: 基本プラットフォームのインストール](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)).  


|                    [サーバー]                    |                                                                                                                                           ハードウェアの推奨事項                                                                                                                                            |                                                                                                                                                   ソフトウェア要件                                                                                                                                                    |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|             ドメイン コント ローラー             |                                                                                                                                             -1 つのネットワーク アダプター                                                                                                                                             |                                       Microsoft Windows Server 2012 R2 または 2012<br />Microsoft[!INCLUDE[btsAD](../../includes/btsad-md.md)]サーバー<br />ドメイン ネーム サーバー (DNS)                                       |
|           Microsoft SQL server            | -2 つのネットワーク アダプター<br />-記憶域エリア ネットワーク (SAN) ディスクの場合省略可能: が、平均スループット、ピーク時のスループット、プラスのピーク スループット時に必要なハード_ディスク領域を選択してメッセージのサイズを平均します。 SAN は、3 つのドライブにパーティション分割する必要があります。 データ、トランザクション ログ、およびクォーラムします。 |                                                                        Microsoft Windows Server 2012 R2 または 2012<br />-   [!INCLUDE[SQLServer2008or2005](../../includes/sqlserver2008or2005-md.md)]                                                                         |
|       BizTalk サーバー メッセージング        |                                                                                                                                            -2 つのネットワーク アダプター                                                                                                                                             |                                                  Microsoft Windows Server 2012 R2 または 2012<br />-BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]                                                   |
| BizTalk HTTP フロント エンド サーバー (MRSR サイト) |                                                                                                                                            -2 つのネットワーク アダプター                                                                                                                                             | Microsoft Windows Server 2012 R2 または 2012<br />-インターネット インフォメーション サービス (IIS)<br />ルーティングが有効なメッセージ キュー サービス<br />-BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] |
|     オーケストレーションの BizTalk サーバー     |                                                                                                                                             -1 つのネットワーク アダプター                                                                                                                                             |                                                  Microsoft Windows Server 2012 R2 または 2012<br />-BizTalk Server<br />-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]                                                   |

