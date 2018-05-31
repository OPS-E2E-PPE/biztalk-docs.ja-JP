---
title: ランプでと傾斜 Off |Microsoft ドキュメント
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
ms.openlocfilehash: a0aafa69315dba07219ad8510c77cdc9de2d4bce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294562"
---
# <a name="on-ramps-and-off-ramps"></a>ランプで、ランプ オフ
環境で、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]が展開されると、BizTalk 受信場所が担当する「入り口です」と呼びます ESB 宛てのメッセージの受信。 ESB 入り口に標準の BizTalk 受信場所を構成する受信場所を関連付ける、toolkit の一部として提供されるパイプラインのいずれかと決定またはの日程を読み取るには、そのパイプラインのコンポーネントを正しく構成しますシナリオに応じて、受信メッセージ。  
  
 ESB「出口」は、BizTalk の動的送信ポートに対応します。 日程が処理されている、値はシステム Properties.xsd スキーマを使用して、関連付けられているメッセージのコンテキスト プロパティに昇格されます。 BizTalk パブリッシュ/サブスクライブ メカニズムで昇格これら送信ポート (出口) メッセージ配信を完了するには動的でメッセージをルーティングするプロパティです。  
  
 次の表は、上のランプによって提供される、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
|名前|メッセージ交換パターン|**Description**|  
|----------|------------------------------|---------------------|  
|ESB です。ItineraryServices|一方向|ASMX 入り口です。SOAP ヘッダー内では、ESB itinerary コンテンツが必要ですが。|  
|ESB です。ItineraryServices.Response|要求-応答|ASMX 入り口です。SOAP ヘッダー内では、ESB itinerary コンテンツが必要ですが。|  
|ESB です。ItineraryServices.WCF|一方向|Windows Communication Foundation (WCF) の入り口です。SOAP ヘッダー内では、ESB itinerary 参照が必要です。|  
|ESB です。ItineraryServices.Response.WCF|要求-応答|WCF の入り口です。SOAP ヘッダー内では、ESB itinerary 参照が必要です。|  
|ESB です。ItineraryServices.Generic.WCF|一方向|WCF の入り口です。要求メッセージだけが必要です。|  
|ESB です。ItineraryServices.Generic.Response.WCF|要求-応答|WCF の入り口です。要求メッセージだけが必要です。|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]上のランプれない ASMX は、ESB 行程を選択するように構成する必要があります。 ESB 行程を選択する方法の詳細については、次を参照してください。[パイプライン コンポーネントを使用して、既存の日程を選択する](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)です。