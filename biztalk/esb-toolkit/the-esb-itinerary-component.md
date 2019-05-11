---
title: ESB スケジュール コンポーネント |Microsoft Docs
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
ms.openlocfilehash: d0e92c62f0ae764ed8123c578d7bc2975d4b10b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399797"
---
# <a name="the-esb-itinerary-component"></a>ESB スケジュール コンポーネント
ESB スケジュール コンポーネントは、ESB オンランプ入り口に、メッセージと共に送信される SOAP ヘッダー コンテキスト プロパティを設定します。  
  
## <a name="installation"></a>インストール  
 ESB コアを自動的にインストールするインストール、**行程**BizTalk Server パイプライン コンポーネント フォルダー内のパイプライン コンポーネント。  
  
## <a name="how-it-works"></a>しくみ  
 ESB スケジュール コンポーネントは、受信パイプラインにのみ配置できる Microsoft BizTalk パイプライン コンポーネントです。 SOAP メッセージのヘッダーまたはプロパティとしてメッセージ コンテキストにコンポーネントの設定のいずれかから値を昇格します。 提供される日程 Web サービスで SOAP ヘッダーの昇格の例が見つかります[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。 これらの Web サービス、コントラクトの一部として SOAP ヘッダーを公開して、クライアント アプリケーションは、ヘッダーを設定する必要があります。 コンポーネントは、SOAP ヘッダー プロパティ (書き込み) を昇格し、値を読み取りますメッセージは、受信パイプラインでコンポーネントを通過して、メッセージ コンテキスト プロパティにすることです。  
  
## <a name="using-the-esb-itinerary-component"></a>ESB スケジュール コンポーネントを使用します。  
 ESB スケジュール コンポーネントを受信パイプラインに追加し、受信場所のパイプラインを使用できます。 コンポーネントには、SOAP ヘッダーの値またはコンポーネントの設定、受信メッセージのコンテキスト プロパティに自動的に昇格させます。  
  
 このコンポーネントを使用する方法の例は、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。