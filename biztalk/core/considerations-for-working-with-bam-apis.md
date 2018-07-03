---
title: BAM Api を使用した際の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd8ccf63-6989-4ad6-a193-cf3043e9a466
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416f8acca6412b8809d7843de7d8084d3df9efc1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005203"
---
# <a name="considerations-for-working-with-bam-apis"></a>BAM API を使用する際の考慮事項
DirectEventStream、BufferedEventStream、MessagingEventStream、OrchestrationEventStream などの "Microsoft.BizTalk.Bam.EventObservation.EventStream" オブジェクトを使用する場合、BAM では、協定世界時 (UTC) 形式 (グリニッジ標準時とも呼ばれます) で自動的に記録されたマイルストーンが表示されます。 API を使用して BAM に日時を送信する場合、日時は UTC 形式に変換されず、送信どおりの形式で受信されます。 BAM ソリューションを開発する場合は、次の注意事項を考慮する必要があります。  
  
- BizTalk Server で追跡されるデータは UTC 形式で受信されます。 このデータは、イベント ストリームから取得した他のデータと一貫性がない場合があります。  
  
- イベント ストリーム API を使用して、日時の追跡データをローカル時刻形式で指定すると、BAM データのすべての時刻は UTC 形式であることが求められるため、BAM ポータルのデータが正しくなくなります。  
  
  現在アップグレード中の既存のアプリケーションがローカル時刻を使用しているときに、BAM ポータルを使用することを計画する場合、データを変更して UTC 形式に準拠させる必要があります。 同様に、カスタム アプリケーションも変更して、UTC 形式に変換する必要があります。  
  
## <a name="see-also"></a>参照  
 [BAM ソリューションを実装します。](../core/implementing-bam-solutions.md)