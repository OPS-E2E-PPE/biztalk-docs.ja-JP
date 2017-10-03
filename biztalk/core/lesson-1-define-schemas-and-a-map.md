---
title: "レッスン 1: 定義のスキーマとマップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: enterprise application integration tutorial, creating solutions
ms.assetid: 4fe7720d-722e-4fa0-a556-477fc66ffa12
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce6411a7a4ffa80b72bad2d84766bf773bbfb42f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-1-define-schemas-and-a-map"></a>レッスン 1: スキーマおよびマップの定義
このレッスンでは、エンタープライズ アプリケーション統合 (EAI) ソリューションに、最初のプロジェクトを作成してビルドします。 このプロジェクトには、2 つのメッセージ スキーマと 1 つのマップが含まれます。  
  
 EAI ソリューションでは、倉庫システムから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に在庫補充要求メッセージが送信され、処理に充てられます。 このレッスンでは、次の項目を作成します。  
  
-   EAI ソリューション (プロジェクトを格納)。  
  
-   プロジェクト (スキーマおよびマップを格納)。  
  
-   スキーマ (倉庫から [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信される在庫補充要求メッセージ用)。  
  
-   スキーマ (要求が拒否されたときに倉庫で予期されるメッセージ用)。  
  
-   マップ (要求拒否メッセージを作成するための要求メッセージの再フォーマット用)。  
  
 最後に開始する前にプロジェクトをビルドする[レッスン 2: ビジネス プロセスの定義](../core/lesson-2-define-the-business-process.md)です。 レッスン 2 では、メッセージをルーティングし、在庫補充要求メッセージの内容が承認条件を満たすかどうかを評価するビジネス プロセスを作成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md)  
  
-   [手順 2: 在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md)  
  
-   [手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md)  
  
-   [手順 4: マップを作成します。](../core/step-4-create-the-map.md)  
  
-   [手順 5: EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md)  
  
## <a name="see-also"></a>参照  
 [このチュートリアルを開始する前に](../core/before-you-begin-the-tutorial.md)   
 [レッスン 2: ビジネス プロセスを定義します。](../core/lesson-2-define-the-business-process.md)   
 [レッスン 3: ソリューションを配置します。](../core/lesson-3-deploy-the-solution.md)