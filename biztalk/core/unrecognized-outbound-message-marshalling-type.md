---
title: 認識されないの送信メッセージをマーシャ リングの種類 |Microsoft Docs
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
ms.openlocfilehash: 46ce69344cc642836f4eb82af6eda84bf40798a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396049"
---
# <a name="unrecognized-outbound-message-marshalling-type"></a>認識されない送信メッセージの型をマーシャ リング
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    イベント ID     |                                           0                                            |
|  イベント ソース   |                                           0                                            |
|    コンポーネント    |                                           0                                            |
|  シンボル名  |                                           0                                            |
|  メッセージ テキスト   | 認識されない送信メッセージの型をマーシャ リングUseBodyElement または UseTemplate が必要です |
  
## <a name="explanation"></a>説明  
 WCF です。OutboundBodyLocation プロパティは、カスタム パイプライン コンポーネントまたはオーケストレーションの UseBodyElement または UseTemplate とは異なる値に設定されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 WCF を設定します。有効な値に OutboundBodyLocation プロパティです。 有効な値は"UseBodyElement"または"UseTemplate"これは、コードを変更します。   
送信メッセージの詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [WCF アダプター コンテキスト プロパティによる動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [WCF アダプターの構成](../core/configuring-the-wcf-adapters.md)