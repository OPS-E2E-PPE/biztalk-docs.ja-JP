---
title: スケジュール オンランプ Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7551974-b9d2-4ae3-b54c-3aa5ba058e95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e0f30d93514fded12d20a06d9fa27fbcd632bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980715"
---
# <a name="the-itinerary-on-ramp-web-services"></a>スケジュール オンランプ Web サービス
旅行プランの Web サービスは、itinerary 入り口行程サービスによって、Microsoft BizTalk のターゲットにし、それ以降の処理や ESB 操作のメッセージを送信するクライアントを許可するメソッドを公開します。  
  
 旅行プランの Web サービス ペイロードを渡します ESB 行程のパイプライン コンポーネントでこれらのサービスが定義されていることを確認する旅行プランを検証、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]構成します。 コンポーネントは、特別なコンテキスト プロパティを検証済みのスケジュールを含むメッセージに追加します。  
  
 場合は、汎用的なスケジュール オンランプ入口、日程を格納している SOAP ヘッダーはメッセージの送信中に指定されていません。 したがって、ESB スケジュール セレクターのパイプライン コンポーネントは、ESB 行程のパイプライン コンポーネントの代わりに使用されます。 ESB スケジュール セレクターのパイプライン コンポーネントが、定義済みの競合回避モジュールの接続文字列に基づいてスケジュールを解決し、ESB 行程のパイプライン コンポーネントを提供するのと同じ検証を提供します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一方向の両方をサポートするサービスをスケジュールおよび要求-応答メッセージ交換パターンの 2 つのバリエーションが含まれています。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ASP.NET (ASMX) および Windows Communication Foundation (WCF) のバージョンのこれらのサービスの両方が含まれています。 ジェネリック バージョンの WCF サービスを提供します。  
  
 指定された一方向のスケジュール サービスの名前は**ESB します。ItineraryService**、 **ESB します。ItineraryServices.WCF**、および**ESB します。ItineraryServices.Generic.WCF**します。  
  
 指定された双方向のスケジュール サービスの名前は**ESB します。ItineraryServices.Response**、 **ESB します。ItineraryServices.Response.WCF**、および**ESB します。ItineraryServices.Generic.Response.WCF**します。  
  
 旅行プランの Web サービスの各は、次のメソッドを公開します。  
  
- **SubmitRequest**します。 このメソッドの ASMX ベースのサービスのインスタンスを受け取り、 **XmlNode**を送信するメッセージを含むクラスです。 WCF ベースのサービスには、このメソッドは、送信するメッセージを含む XML 文字列を受け取ります。  
  
- **SubmitRequestResponse**します。 ASMX ベースのサービスには、このメソッドのインスタンスへの参照を受け取ります、 **XmlNode**クラスを送信するメッセージを含み、のインスタンスで、応答メッセージを返す、 **XmlNode**に渡されます。です。 WCF ベースのサービスの場合、このメソッドはへの参照を**オブジェクト**を送信するメッセージを含みの配列を返す XML 文字列である型**XmlNodes**で、 **オブジェクト**に渡されました。  
  
  旅行プランの Web サービスの使用に関する詳細については、次を参照してください。[をインストールすると、日程ランプでサンプルを実行する](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)します。  
  
> [!NOTE]
>  既定では、旅行プランの Web サービスはセキュリティで保護の Sockets Layer (SSL) クライアントがアクセスするときに要求するように構成されていません。 クライアント アクセス用の SSL を必要とし、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec を使用して ESBExceptions データベースをホストするサーバー間の接続を保護し、適切なサービスを構成する必要があります。ファイル レベルのアクセス制御リスト (ACL) のアクセス許可。