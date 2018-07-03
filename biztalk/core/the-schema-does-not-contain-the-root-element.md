---
title: スキーマにルート要素が含まれていない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efc33f2b-9e14-4d2e-8c8a-32b7696f80ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc2191a5d9ea891efa285d8fc5006f243319fde5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008443"
---
# <a name="the-schema-does-not-contain-the-root-element"></a>スキーマにルート要素が含まれていません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                             SchemaCode102ENullRootElement                              |
|  メッセージ テキスト   |                    スキーマにルート要素が含まれていません {0}                    |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージの検証に使用されるスキーマにルート要素が含まれていなかったため、受信パイプラインで受信メッセージを処理できなかったか、または送信パイプラインで送信メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ドキュメント スキーマの展開を解除し、ルート要素をスキーマに追加して、スキーマを再展開します。