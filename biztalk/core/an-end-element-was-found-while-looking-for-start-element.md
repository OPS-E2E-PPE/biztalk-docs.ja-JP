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
ms.openlocfilehash: b44cd404242c19ebbfbc92b358fb33de9b510b95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360191"
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a>開始要素の中に、終了要素が見つかりました
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
 このエラー/警告/情報イベントは、BizTalk Server を処理できなかったこと (解析後) 受信 XML メッセージまたは送信 XML メッセージ (シリアル化) する前に、XML メッセージの検証に失敗したためことを示します。 XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加してし、メッセージを再送信します。