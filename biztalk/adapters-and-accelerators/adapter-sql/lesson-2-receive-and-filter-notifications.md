---
title: レッスン 2:受信して通知をフィルター処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5ec679c-1c67-4bf4-aa88-0787373343f5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d2814065e188f72d42b444e04ad11ace0194d6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368877"
---
# <a name="lesson-2-receive-and-filter-notifications"></a>レッスン 2:受信して通知をフィルター処理
変更の通知を受信するオーケストレーションの作成を開始するこのレッスンで、**従業員**テーブル。 通知で通知の種類は、挿入操作のかどうかの型を抽出し、オーケストレーションは、通知を受信後、**従業員**テーブル、"if"条件を使用して後続のタスクを実行します。 このレッスンでは、次のタスクを行います。  
  
1.  追加、一方向受信ポートと**受信**通知メッセージを受信するオーケストレーションに図形。  
  
2.  追加、**式**通知の種類を抽出する xpath クエリを格納している図形。  
  
3.  通知の種類がわかったら、フィルターを追加、オーケストレーションを含めることによって、**判断**図形。 この図形は、通知が挿入通知し、後続の操作を実行するかどうかを決定します。 挿入操作では、通知がない場合、オーケストレーションは何も行いません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: 通知を受信するためのオーケストレーション図形を追加する](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [手順 2:通知メッセージから通知の種類を抽出する](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [ステップ 3:挿入通知のフィルターを追加する](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)