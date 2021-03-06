---
title: 送信ポートを使用して、スケジュール サービス サブスクライバーとして |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 898b461c-4d0d-4703-a8ca-7f52f3f15f70
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81ab596b01c515fad670b959c00e0571b5e9962c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396480"
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a>スケジュール サービス サブスクライバーとして送信ポートを使用します。
スケジュール サービス サブスクライバーとして送信ポートを使用する方法の例としては、図 1 を次の条件を満たすメッセージを取得する動的な一方向送信ポートのフィルター条件を示します。  
  
- **IsRequestResponse = False**  
  
- **ServiceName = DynamicTest**  
  
- **ServiceState = 保留中**  
  
- **ServiceType メッセージングを =**  
  
  ![送信ポート](../esb-toolkit/media/ch4-sendport.gif "Ch4 SendPort")  
  
  **図 1**  
  
  **送信ポート フィルターの例**  
  
  送信ポートのフィルター式を使用するが選択 itinerary の傾斜を使用して、メッセージ ボックス データベースからメッセージのプロパティと値のセットを指定します。  
  
> [!NOTE]
>  できるだけ; フォーカスがある、特定のフィルター条件を使用することが重要それ以外の場合、意図しないメッセージは、大規模環境で問題が発生する可能性がありますのリスクがあります。 システム Properties.xsd スキーマでは、サブスクリプションのフィルターのプロパティを定義します。