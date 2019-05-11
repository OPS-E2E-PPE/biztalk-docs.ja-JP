---
title: サービス管理のパターン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fea915c-0074-472e-909b-fbbd88d7359c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ec777e46dada4a47f00cff666b6924e448ef8b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392031"
---
# <a name="service-management-patterns"></a>サービス管理パターン
## <a name="repair-and-resubmit"></a>修復と再送信  
 修復と再送信のパターンをサービスがメッセージを処理できないとを正常に失敗したメッセージの形式でその状態を外部化を修復し、サービスに再送信できるメッセージの内容を有効にする必要があるソリューションを定義しますメッセージの処理を続行します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] 追加の操作のメカニズムでは、Microsoft BizTalk メッセージングとオーケストレーションの例外正規化できが公開されているが含まれています。 ESB ソリューションを設計するには、これが例外を処理する方法のアカウントに重要です。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外を表示および管理する方法を示すサンプル ESB 管理ポータル アプリケーションが含まれています。 ESB 管理ポータルのサンプル アプリケーションを使用して例外を再送信の修復と詳細については、次を参照してください。[修復と再送信メッセージ](../esb-toolkit/repairing-and-resubmitting-messages.md)します。