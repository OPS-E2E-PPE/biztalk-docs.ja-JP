---
title: サービス ネットワーク管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21469dad-6c64-470a-bd58-8309d789ce6c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4280438758e3f2626cf2e0ec68c1e30f51d0bde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268894"
---
# <a name="service-network-management"></a>サービス ネットワーク管理
実行時の効果的な管理には、実行時環境にデプロイされているサービスの知識が必要です。 AmberPoint SMS には、実際に受信場所と、図 1 に示すように、BizTalk 管理グループ内にデプロイされたポートを送信を検出できます。  
  
 ![AmberPoint コンテナーの検出](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9 AmberPointContainerDiscovery")  
  
 **図 1**  
  
 **AmberPoint コンテナーの検出を SMS 画面**  
  
 AmberPoint SMS 情報を使用して、デプロイされたサービスで、ユーザーが実行時構成を理解し、実行中の他のサービスへの依存関係を理解に役立つサービスのさまざまなパースペクティブが表示サービスのネットワーク。 図 2 は、サービスのプロファイルとの依存関係の画面を示しています。  
  
 ![AmberPoint サービス プロファイル](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9 AmberPointServiceProfile")  
  
 **図 2**  
  
 **SMS の AmberPoint サービス プロファイルとの依存関係画面**  
  
 AmberPoint SMS に公開したりなどに、既存の Universal Description, Discovery, と Integration (UDDI) レジストリ、カスタム構成の管理リポジトリ、and マスター システム管理コンソールでは、サービスの検出と実行時のメタデータを転送できます。Microsoft Operations Manager (MOM) 2004 と System Center Operations Manager 2007 (SCOM)。