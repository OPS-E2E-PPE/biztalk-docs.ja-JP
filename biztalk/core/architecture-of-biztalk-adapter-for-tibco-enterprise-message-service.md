---
title: BizTalk Adapter for TIBCO Enterprise Message Service のアーキテクチャ |Microsoft ドキュメント
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
ms.openlocfilehash: 88c7bc6420efb67085e4f3a05f6daf0c5dbd2feb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230282"
---
# <a name="architecture-of-biztalk-adapter-for-tibco-enterprise-message-service"></a>BizTalk Adapter for TIBCO Enterprise Message Service のアーキテクチャ
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) は、TIBCO EMS システムと BizTalk Server との間でリアルタイムのビジネス データを交換する手段を提供します。 このアダプターによって、XML アプリケーションと TIBCO EMS との対話処理が可能になります。  
  
 このアダプターは、次のいずれかを使用して、BizTalk アプリケーションが TIBCO EMS と通信できるようにする XML メッセージを受け入れます。  
  
-   **送信アダプター**: 静的な一方向送信ポートを使用して TIBCO EMS にメッセージを送信します。  
  
-   **受信アダプター**: 使用して静的な一方向の受信ポートを TIBCO EMS からメッセージを受信します。  
  
## <a name="one-way-send-operation"></a>一方向の送信操作  
 次の図は、BizTalk Adapter for TIBCO EMS を使用した一方向の送信操作のアーキテクチャを示しています。  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
## <a name="one-way-receive-operation"></a>一方向の受信操作  
 次の図は、BizTalk Adapter for TIBCO EMS を使用した一方向の受信操作のアーキテクチャを示しています。  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>参照  
 [アダプターの機能](../core/adapter-features.md)   
 [計画とアーキテクチャ](../core/planning-and-architecture16.md)