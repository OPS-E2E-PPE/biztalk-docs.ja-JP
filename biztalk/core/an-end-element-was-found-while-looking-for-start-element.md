---
title: 開始要素の中に、終了要素が見つかりました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e200f4ffd8d822a5c2bb1a0bad74a60e84a408a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992435"
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a>StartElement の検索中に EndElement が見つかりました
## <a name="details"></a>詳細  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  製品名   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| 製品バージョン |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    イベント ID     |                                                 -                                                 |
|  イベント ソース   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI       |
|    コンポーネント    |                                            EDI エンジン                                             |
|  シンボル名  |                             EndElementFoundWhenLookingForStartElement                             |
|  メッセージ テキスト   | 名前の EndElement{0}検出されましたが、名前の StartElement の検索中に{1}、深さ {2} |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、XML メッセージが検証に失敗したため、BizTalk Server が受信 XML メッセージ (解析後) または送信 XML メッセージ (シリアル化前) を処理できなかったことを示します。 XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加し、メッセージを再送信します。