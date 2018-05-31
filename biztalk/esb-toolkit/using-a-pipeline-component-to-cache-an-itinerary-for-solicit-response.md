---
title: 送信請求-応答の日程をキャッシュするパイプライン コンポーネントを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add07ebf-785c-4c53-be69-efd40677a758
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b6822a4f4ca70e88ee86277e00645982595b47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294994"
---
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a>パイプライン コンポーネントを使用して、送信請求-応答の日程をキャッシュするには
送信するメッセージ、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary 入り口は旅程を一方向または双方向 (要求-応答) 行程経由させることです。 要求-応答の日程をサポートするには、itinerary メカニズムは BizTalk 動的な送信請求-応答送信ポートのキャッシュを提供する必要があります。  
  
 ESB 行程キャッシュのパイプライン コンポーネントは、キャッシュ発信メッセージ コンテキストに保存されている旅程を配置し、応答メッセージにアタッチ構成可能なキャッシュ キーを使用して、送信ポートによって返されます。 これにより、itinerary サービスを処理し、旅行計画に現在のサービスの後に定義されている後続のサービスを実行できます。  
  
 ESB 行程キャッシュ パイプライン コンポーネントは、既定では、図 1 に示すように ItineraryReceiveSend BizTalk パイプラインに存在します。 このパイプラインは、送信請求-応答送信ポートの受信パイプラインとしてのみ使用する必要があります。  
  
 ![パイプライン コンポーネントのキャッシュ](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4 PipelineComponentCache")  
  
 **図 1**  
  
 **ESB 行程キャッシュ パイプライン コンポーネント**  
  
 使用する BizTalk の ESB 行程キャッシュ パイプライン コンポーネントは、送信請求-応答送信ポートのパイプラインを受信します。