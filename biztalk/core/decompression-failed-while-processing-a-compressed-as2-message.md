---
title: 圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5246ee97-cc60-4878-9447-de870c0f4c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 424dded28973b2e113c959eacd9141fbaf2fb95d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390293"
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a>圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |       圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。 エラー: {0}       |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを解凍できませんでしたを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   AS2 メッセージの圧縮ラッパーが有効であることを確認します。  
  
-   (受信メッセージのプロパティがプロパティのチェックを上書きする) 場合、「メッセージを圧縮する必要があります」プロパティが AS2 メッセージの送信者 ページ、AS2 のプロパティ ダイアログ ボックスのチェックされてパーティに対して確認することにより、BizTalk server、圧縮解除が有効になっていることを確認します.  
  
-   エラー メッセージ テキストで指定されたエラーの説明を使用すると、特定の問題を識別します。