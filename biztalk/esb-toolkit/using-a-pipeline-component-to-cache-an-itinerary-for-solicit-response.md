---
title: 送信請求-応答の日程をキャッシュするパイプライン コンポーネントを使用して |Microsoft Docs
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
ms.openlocfilehash: 5ddb3f639286ba29e28230b53b9a8a26a8304ea1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396504"
---
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a>パイプライン コンポーネントを使用して、送信請求-応答の日程をキャッシュするには
使用して送信されたメッセージ、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ランプでの旅程旅程を一方向または双方向 (要求-応答) のスケジュールのいずれかを実行します。 要求-応答のスケジュールをサポートするために BizTalk の動的な送信請求-応答送信ポートのキャッシュ スケジュール メカニズムを提供する必要があります。  
  
 ESB スケジュール キャッシュのパイプライン コンポーネントは、送信メッセージのコンテキスト、キャッシュに格納されているスケジュールし、応答メッセージにアタッチしますこれは、構成可能なキャッシュ キーを使用して送信ポートによって返されます。 これにより、スケジュールのサービスを処理し、旅行プランでは、現在のサービスの後に定義されている後続のサービスを実行できます。  
  
 ESB スケジュール キャッシュのパイプライン コンポーネントは、既定で図 1 に示すように、ItineraryReceiveSend BizTalk パイプラインに存在します。 このパイプラインは、送信請求-応答送信ポートの受信パイプラインとしてのみ使用する必要があります。  
  
 ![パイプライン コンポーネントのキャッシュ](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4 PipelineComponentCache")  
  
 **図 1**  
  
 **ESB スケジュール キャッシュ パイプライン コンポーネント**  
  
 使用して、biztalk ESB 行程キャッシュ パイプライン コンポーネントには、送信請求-応答送信ポートのパイプラインが表示されます。