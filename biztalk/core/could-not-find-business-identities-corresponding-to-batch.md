---
title: バッチに対応するビジネス Id が見つかりませんでした |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9baf11-e9c6-482d-a47d-aa99852939bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d9d49d4fe30f8e3dd85f32c17e834f45550024d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354362"
---
# <a name="could-not-find-business-identities-corresponding-to-batch"></a>バッチに対応するビジネス Id が見つかりませんでした。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                               IdentitiesNotFoundForBatch                               |
|  メッセージ テキスト   |             バッチに対応するビジネス Id が見つかりませんでした。{0}します。             |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、データが不十分なために BizTalk Server がバッチ メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、示された ID のバッチが親アグリーメントの [アグリーメントのプロパティ] に含まれていること、および正しいビジネス ID がアグリーメントに指定されていることを確認します。