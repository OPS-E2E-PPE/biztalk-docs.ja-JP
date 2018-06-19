---
title: 'レッスン 2: 表示され、通知をフィルター処理 |Microsoft ドキュメント'
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
ms.openlocfilehash: 0f28d0479510078b3717d68f99976808ee19aa7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222554"
---
# <a name="lesson-2-receive-and-filter-notifications"></a>レッスン 2: 表示され、通知をフィルター処理
このレッスンで開始するへの変更の通知を受信するオーケストレーションを作成、**従業員**テーブル。 通知とかどうか、通知の種類の挿入操作の種類を抽出し、オーケストレーションは、通知を受信した後、**従業員**テーブル、"if"条件を使用して後続のタスクを実行します。 このレッスンでは、次のタスクを行います。  
  
1.  追加、一方向受信ポートと**受信**通知メッセージを受信するオーケストレーションに図形です。  
  
2.  追加、**式**通知の種類を抽出する xpath クエリを含む図形です。  
  
3.  通知の種類がわかっている後にフィルターを追加、オーケストレーションを含めることによって、**判断**図形です。 この図形は、通知が挿入の通知し、後続の操作を実行するかどうかを決定します。 挿入操作の通知がない場合は、オーケストレーションは何も実行されません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: 通知を受信するオーケストレーション図形を追加します。](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [手順 2: 通知メッセージからの通知の種類を抽出します。](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [手順 3: 挿入の通知にフィルターを追加します。](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)