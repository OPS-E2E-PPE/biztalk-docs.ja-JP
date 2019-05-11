---
title: オンランプとオフランプ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0cce5d2-f16f-4bda-94ac-20c4f457cfc7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 528a8a42319fce4dbfc6507ec4d0658092e44963
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400052"
---
# <a name="on-ramps-and-off-ramps"></a>オンランプとオフランプ
環境で、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]が展開されると、BizTalk 受信場所が担当する「入り口」と呼びます ESB 宛てのメッセージの受信。 ESB 入り口を標準の BizTalk 受信場所を構成するには、受信場所を toolkit の一部として提供されているパイプラインのいずれかと関連付けるおよび決定またはの旅程を読み取り、そのパイプラインのコンポーネントを正しく構成しますシナリオに応じて受信メッセージ。  
  
 ESB「オフ ランプ」は、BizTalk の動的送信ポートに対応します。 日程が処理されると、値は、システム Properties.xsd スキーマを使用して、関連付けられているメッセージのコンテキスト プロパティに昇格されます。 BizTalk パブリッシュ/サブスクライブこれら昇格メカニズムは送信ポート (傾斜オフ) メッセージ配信を完了する動的な経由でメッセージをルーティングするプロパティ。  
  
 次の表は、オンランプによって提供される、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
|名前|メッセージ交換パターン|**[説明]**|  
|----------|------------------------------|---------------------|  
|ESB します。ItineraryServices|一方向|ASMX のランプ;SOAP ヘッダーでは ESB オンランプ コンテンツが必要です。|  
|ESB します。ItineraryServices.Response|要求-応答|ASMX のランプ;SOAP ヘッダーでは ESB オンランプ コンテンツが必要です。|  
|ESB します。ItineraryServices.WCF|一方向|Windows Communication Foundation (WCF) に増加します。SOAP ヘッダーでは ESB スケジュールの参照が必要です。|  
|ESB します。ItineraryServices.Response.WCF|要求-応答|WCF - 傾斜します。SOAP ヘッダーでは ESB スケジュールの参照が必要です。|  
|ESB します。ItineraryServices.Generic.WCF|一方向|WCF - 傾斜します。要求メッセージのみを想定しています。|  
|ESB します。ItineraryServices.Generic.Response.WCF|要求-応答|WCF - 傾斜します。要求メッセージのみを想定しています。|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] オンランプ ASMX を構成して、ESB 行程を選択する必要がないです。 ESB スケジュールを選択する方法の詳細については、次を参照してください。[パイプライン コンポーネントを使用して、既存のスケジュールを選択する](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)します。