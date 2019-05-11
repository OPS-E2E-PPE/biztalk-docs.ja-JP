---
title: MQSeries アダプターのカスタム ヘッダー |Microsoft Docs
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
ms.openlocfilehash: 758b0bb33be70f681d4d7ef732e50555d6eca026
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323790"
---
# <a name="mqseries-adapter-custom-headers"></a>MQSeries アダプターのカスタム ヘッダー
MQSeries メッセージで使用されるヘッダー構造、ために使用するカスタム ヘッダーを管理する必要があります。 カスタム ヘッダーは、MQSeries ヘッダーの処理を妨げることを回避するために、メッセージ本文の一部である必要があります。 自動的に昇格されたプロパティの降格を避けることを確認します。 自動的に昇格されるプロパティの詳細については、次を参照してください。 [MQSeries アダプター プロパティ](../core/mqseries-adapter-properties.md)します。  
  
 さらに、メッセージの本文にカスタム ヘッダーを組み込むことでは、追加の処理が必要です。 1 つのソリューションでは、アプリケーションのパイプラインでカスタム ヘッダーを処理します。 受信パイプラインは、カスタム ヘッダー情報を抽出し、コンテキスト プロパティと情報を昇格させます。 同様に、送信パイプラインでは、カスタム ヘッダーに対応するコンテキスト プロパティは、し、メッセージの本文のプロパティを降格させます。  
  
 パイプライン コンポーネントでカスタム ヘッダーの使用の例は、次を参照してください。 [MQSSendPipelineComponent (BizTalk Server サンプル)](../core/mqssendpipelinecomponent-biztalk-server-sample.md)します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプター プロパティ](../core/mqseries-adapter-properties.md)