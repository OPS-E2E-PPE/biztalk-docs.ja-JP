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
ms.openlocfilehash: 630ce4850c2bb11f9b5a18db03204ef2c1e24cae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003731"
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a>受信者 ID を使用してアグリーメントにアクセスできません
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
 このエラーは、送信パイプラインで送信 AS2 メッセージの送信先パーティを決定できなかったことを示します。送信パイプラインは、送信メッセージの AS2To コンテキスト プロパティまたは Http.UserHttpHeaders コンテキスト プロパティの AS2To プロパティと、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページにある AS2-To プロパティのパーティの名前を照合できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページにある AS2-To プロパティを、エラーになった AS2 メッセージに関連付けられた適切なパーティ名に設定します。