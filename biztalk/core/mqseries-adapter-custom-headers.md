---
title: MQSeries アダプターのカスタム ヘッダー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, custom headers
ms.assetid: b0e18203-a33f-4d50-8483-396699cdff23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09a05b8c73cd7be84af01eb4465681816e429bc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263090"
---
# <a name="mqseries-adapter-custom-headers"></a>MQSeries アダプターのカスタム ヘッダー
MQSeries メッセージで使用されるヘッダー構造が原因で、使用するカスタム ヘッダーの管理が必要になります。 カスタム ヘッダーは、MQSeries ヘッダーの処理に影響を与えないように、メッセージ本文の一部にする必要があります。 自動的に昇格されたプロパティは降格させないようにしてください。 自動的に昇格されるプロパティの詳細については、次を参照してください。 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)です。  
  
 上記の内容から、カスタム ヘッダーをメッセージ本文に組み込むには、追加処理が必要です。 1 つの解決策は、カスタム ヘッダーをアプリケーションのパイプラインで処理することです。 受信パイプラインでは、カスタム ヘッダー情報を抽出し、その情報をコンテキスト プロパティとして昇格させます。 同様に、送信パイプラインでは、カスタム ヘッダーに対応するコンテキスト プロパティを取得し、それらのプロパティをメッセージ本文内に降格させます。  
  
 パイプライン コンポーネントでカスタム ヘッダーの使用の例は、次を参照してください。 [MQSSendPipelineComponent (BizTalk Server サンプル)](../core/mqssendpipelinecomponent-biztalk-server-sample.md)です。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)