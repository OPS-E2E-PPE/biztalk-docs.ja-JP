---
title: BizTalk Adapter for TIBCO Enterprise Message Service のアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transmit adapter
- one-way receive operations
- architecture
- one-way send operations
- receive adapter
ms.assetid: 304c7236-aacd-4761-8c33-e876b53e84ff
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d1f6735ec5fee445fa5f2403f7ca48d32dfae2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359021"
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a>BizTalk Adapter for TIBCO Enterprise Message Service のアーキテクチャ
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) は、TIBCO EMS システムと BizTalk Server の間のリアルタイムのビジネス データを交換する手段を提供します。 アダプターでは、XML アプリケーションと TIBCO EMS 間操作ができます。  
  
 アダプターは、次のいずれかを使用して TIBCO EMS と通信する BizTalk アプリケーションを有効にする XML メッセージを受け取ります。  
  
-   **送信アダプター**:静的な一方向送信ポートを使用して、TIBCO EMS にメッセージを送信します。  
  
-   **受信アダプター**:TIBCO EMS からメッセージを受信ポートを受信する静的な一方向の使用されます。  
  
## <a name="one-way-send-operation"></a>一方向の送信操作  
 次の図は、BizTalk Adapter for TIBCO EMS の使用の一方向の送信操作のアーキテクチャを示します。  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
## <a name="one-way-receive-operation"></a>一方向の受信操作  
 次の図は、一方向の受信操作が BizTalk Adapter for TIBCO EMS の使用のアーキテクチャを示します。  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>参照  
 [アダプターの機能](../core/adapter-features.md)   
 [計画および設計](../core/planning-and-architecture16.md)