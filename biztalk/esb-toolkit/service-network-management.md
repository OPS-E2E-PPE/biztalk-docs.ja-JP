---
title: "サービスのネットワークの管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21469dad-6c64-470a-bd58-8309d789ce6c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 741abaaa3042cb40f7043b25ce041bb84740f26a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="service-network-management"></a>サービスのネットワーク管理
効果的な実行時の管理には、実行時環境にデプロイされているサービスの知識が必要です。 AmberPoint SMS には、実際の受信場所と送信では、図 1 に示すようを BizTalk 管理グループ内に配置されたポートを検出できます。  
  
 ![AmberPoint コンテナーの検出](../esb-toolkit/media/ch9-amberpointcontainerdiscovery.gif "Ch9 AmberPointContainerDiscovery")  
  
 **図 1**  
  
 **AmberPoint コンテナーの検出を SMS 画面**  
  
 AmberPoint SMS は実行時構成を把握し、実行されている、内の他のサービスへの依存関係を認めるようにユーザーを支援するサービスのさまざまなパースペクティブをデプロイ済みサービスの情報を使用して、サービスのネットワーク。 図 2 は、サービスのプロファイルとの依存関係の画面を示しています。  
  
 ![AmberPoint サービス プロファイル](../esb-toolkit/media/ch9-amberpointserviceprofile.gif "Ch9 AmberPointServiceProfile")  
  
 **図 2**  
  
 **AmberPoint SMS サービスのプロファイルとの依存関係の画面**  
  
 AmberPoint SMS の発行およびなどを既存の Universal Description, Discovery, と Integration (UDDI) レジストリ、カスタム構成管理リポジトリでは、and マスター システム管理コンソールでは、サービスの検出と実行時のメタデータを転送できます。Microsoft Operations Manager (MOM) 2004 と System Center Operations Manager 2007 (SCOM)。