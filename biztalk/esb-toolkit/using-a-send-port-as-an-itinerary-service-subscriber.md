---
title: 送信ポートを使用して、Itinerary サービス サブスクライバーとして |Microsoft ドキュメント
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
ms.openlocfilehash: 5213b22c1bdfaa505dbf4b62a03095bcec5a1746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295490"
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a>Itinerary サービス サブスクライバーとして、送信ポートを使用します。
Itinerary サービス サブスクライバーとして、送信ポートを使用する方法の例は、としては、図 1 は、次の条件に一致するメッセージを取得する動的な一方向送信ポートのフィルター条件を示します。  
  
-   **IsRequestResponse = False**  
  
-   **ServiceName = DynamicTest**  
  
-   **ServiceState = 保留中**  
  
-   **ServiceType メッセージングを =**  
  
 ![送信ポート](../esb-toolkit/media/ch4-sendport.gif "Ch4 SendPort")  
  
 **図 1**  
  
 **送信ポート フィルターの例**  
  
 送信ポートのフィルター式を使用すると、itinerary の増加を使用してメッセージ ボックス データベースからピックアップされますメッセージのプロパティと値のセットを指定します。  
  
> [!NOTE]
>  特定で可能なです。 フォーカスのあるフィルター条件を使用することが重要それ以外の場合、意図しないメッセージは、大容量の環境で問題が発生する可能性がありますのピックアップのリスクがあります。 システム Properties.xsd スキーマでは、サブスクリプションのフィルターのプロパティを定義します。