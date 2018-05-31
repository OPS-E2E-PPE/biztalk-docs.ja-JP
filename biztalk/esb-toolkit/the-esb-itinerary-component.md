---
title: ESB Itinerary コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 379edc6a-7d53-4338-87a5-47b5238453a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80aa7c1ef4bc53ad2e2821eaf8dc4184777900a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294970"
---
# <a name="the-esb-itinerary-component"></a>ESB Itinerary コンポーネント
ESB 行程コンポーネントは、ESB itinerary 入り口に、メッセージと共に送信される SOAP ヘッダー コンテキスト プロパティを設定します。  
  
## <a name="installation"></a>インストール  
 ESB コアを自動的にインストールするとインストール、**行程**BizTalk Server パイプライン コンポーネント フォルダー内のパイプライン コンポーネントです。  
  
## <a name="how-it-works"></a>しくみ  
 ESB 行程コンポーネントは、受信パイプラインにのみ存在でく Microsoft BizTalk パイプライン コンポーネントです。 SOAP メッセージのヘッダーまたはプロパティとしてメッセージ コンテキストにコンポーネントの設定のいずれかの値を昇格します。 提供される行程ランプで Web サービスで SOAP ヘッダーを昇格させるの例を見つけることができます[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 これらの Web サービス、コントラクトの一部として SOAP ヘッダーを公開して、クライアント アプリケーションがヘッダーを設定する必要があります。 コンポーネントが、SOAP ヘッダーの値し、(書き込み) を昇格させますを読み取るように、メッセージは、受信パイプラインのコンポーネントを通過して、メッセージ コンテキスト プロパティにします。  
  
## <a name="using-the-esb-itinerary-component"></a>ESB Itinerary コンポーネントを使用します。  
 ESB 行程コンポーネントは、受信パイプラインに追加し、受信場所、パイプラインを使用できます。 コンポーネントは、SOAP ヘッダーの値または受信メッセージのコンテキスト プロパティにコンポーネントの設定を自動的に昇格させます。  
  
 このコンポーネントを使用する方法の例は、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。