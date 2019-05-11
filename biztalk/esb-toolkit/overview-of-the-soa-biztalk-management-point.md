---
title: SOA BizTalk 管理ポイントの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17a6631135272d2e58571ebdf8c4afed95f967ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400035"
---
# <a name="overview-of-the-soa-biztalk-management-point"></a>SOA BizTalk 管理ポイントの概要
BizTalk 管理ポイントは、ネイティブ SOA サービス マネージャー、Workbench の製品と統合します。 一般的な Web サービスの管理ポイントとは異なりこの実装に関連付けられている BizTalk Server の観点から表される、Microsoft BizTalk Server 環境によって提供されるサービスの場所の受信し、送信ポート。 任意のため、これらのサービスが、Web サービスに必ずしも関連付けられていないが、SOA サービス マネージャーの観点から Web サービスとして扱えるの性質は、受信場所と送信ポート (さまざまな BizTalk Server アダプターに対して構成されている)SOA Workbench。  
  
 図 1 は、アプリケーションの例の Workbench ページを表示する SOA Service Manager Web アプリケーションを示します。 左側のツリー ビューにより、ユーザーがアプリケーションと、BizTalk Server 内にインストールされているサービスを移動して、右側のペインは、アプリケーションの詳細、操作、アクセス ポート、カテゴリ、ルール、および監視情報を表示するユーザー。  
  
 ![Ch9&#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9 SOAServiceManager")  
  
 **図 1**  
  
 **Workbench のページで使用可能な監視機能を示す、SOA サービス マネージャー**  
  
 すべての (すべての送信ポートし、受信場所)、アプリケーション内の操作や特定の操作を監視することができます。Workbench の表示、選択した通過するメッセージの一覧は、送信ポートと受信場所。 リスト内のメッセージをダブルクリックすると、Workbench は、(記録を有効になっている) 場合、メッセージとそのコンテキスト プロパティの詳細を表示します。 または、そのサービスを通過するリアルタイムのメッセージでは、特定のサービスとモニターを選択できます。