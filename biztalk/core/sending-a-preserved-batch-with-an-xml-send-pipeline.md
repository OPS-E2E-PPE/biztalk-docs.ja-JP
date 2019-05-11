---
title: 送信パイプラインの XML による保存されたバッチの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6765576a-134f-4856-911c-2f603b6479bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ea7a208942895c11a633fa0a67ae583952db0c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399047"
---
# <a name="sending-a-preserved-batch-with-an-xml-send-pipeline"></a>XML 送信パイプラインによる保存されたバッチを送信します。
通常、保存されたバッチは、EDI 送信パイプラインを使用して送信されます。 ただし、保存されたバッチを送信するのに、XML 送信パイプラインを使用することもできます。 生成され、EDI で、MessageBox にドロップされる保存されたバッチから受信パイプラインは、XML 形式では、XML 送信パイプラインは XML 形式のバッチを受け渡しします。  
  
 XML 送信パイプラインを使用して、保存されたバッチを送信するには、該当するバッチ スキーマと、インターチェンジの各メッセージの種類のドキュメント スキーマを持つプロジェクトを展開する必要があります。 さらに、プロジェクト内に展開するバッチ スキーマの名前空間を変更する必要もします。 これを行わない場合、保存されたバッチの XML ファイル内の名前空間は、バッチ スキーマの名前空間に対応していません。 次の表に示すように、バッチ スキーマの名前空間を変更する必要があります。  
  
|このエンコードの種類。|バッチ スキーマでこの名前空間を変更します。|次の名前空間。|  
|-----------------------------|------------------------------------------------|---------------------------------|  
|EDIFACT|`http://schemas.microsoft.com/Edi/Edifact`|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`|  
|X12|`http://schemas.microsoft.com/Edi/X12_BatchSchema`|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`|  
  
 これは、EDI アセンブラーの問題ではありません。  
  
## <a name="see-also"></a>参照  
 [EDI バッチの構成](../core/configuring-edi-batches.md)