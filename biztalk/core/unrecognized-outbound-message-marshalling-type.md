---
title: 送信メッセージの認識できない型をマーシャ リング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e675112b-12f3-47ff-95f7-ce1a05db120e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3928bde0d81a4fe22b7c16af41c3a4b6d5c7121c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286658"
---
# <a name="unrecognized-outbound-message-marshalling-type"></a>送信メッセージのマーシャリングの種類が認識されません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|送信メッセージのマーシャリングの種類が認識されません。UseBodyElement または UseTemplate が必要です。|  
  
## <a name="explanation"></a>説明  
 WCF.OutboundBodyLocation プロパティが、カスタムのパイプライン コンポーネントまたはオーケストレーションの UseBodyElement または UseTemplate とは異なる値に設定されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 WCF.OutboundBodyLocation プロパティを有効な値に設定します。 有効な値は "UseBodyElement" または "UseTemplate" です。これはコードの変更です。   
送信メッセージの詳細については、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [WCF アダプタの構成](../core/configuring-the-wcf-adapters.md)