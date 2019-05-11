---
title: 受信者 id を使用してアクセス契約にできませんでした |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbdd869e244f3d59ebd267d492112a1e29441c2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258493"
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a>受信者 id を使用してアグリーメントにアクセスできません。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                         UnableToLocateAS2PartyByPartyNameError                         |
|  メッセージ テキスト   |                受信者 id を使用してアクセス契約を読み込めません。 {0}                 |
  
## <a name="explanation"></a>説明  
 このエラーを示すこと、送信パイプラインを特定できませんでした、送信 AS2 メッセージのパーティ、送信メッセージの AS2To コンテキスト プロパティまたは Http.UserHttpHeaders コンテキスト プロパティの名前で、AS2To プロパティも一致しないため、AS2 パーティ-AS2 メッセージの受信者] ページ、[AS2 のプロパティ] ダイアログ ボックスの [パーティのプロパティにします。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、設定、AS2 のエラーでは、AS2 メッセージに関連付けられている適切なパーティ名を AS2 のプロパティ ダイアログ ボックスのページを AS2 メッセージの受信者としてのパーティのプロパティ。