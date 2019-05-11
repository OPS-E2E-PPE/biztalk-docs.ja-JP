---
title: AS2 デコーダーで、MDN に返された MIC 値の検証に処理に失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fe2d76d-b0f1-4118-8483-547c2c9fffb7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b65543f3edc47b03f8b1f71344d16c5ff7b9293a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388984"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a>AS2 デコーダーで、MDN に返された MIC 値の検証に処理に失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| 製品バージョン |                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    イベント ID     |                                                                                                   -                                                                                                   |
|  イベント ソース   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                         |
|    コンポーネント    |                                                                                              AS2 エンジン                                                                                               |
|  シンボル名  |                                                                                AS2DecoderMdnMicFailureDuringProcessing                                                                                |
|  メッセージ テキスト   | AS2 デコーダーで、MDN に返された MIC 値の検証に処理できませんでした。  MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、MIC (メッセージ整合性チェック) に検証が失敗したためで受信 MDN が受信パイプラインが処理することを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、元のメッセージの Signed-receipt-micalg ヘッダー) の「MDN の生成に使用されるアルゴリズムは、AS2 メッセージの受信者の Signed-receipt-micalg プロパティで指定されたアルゴリズムと同じことを確認します。 SHA1 または MD5 のどちらかがどちらもあります。 指定されたアルゴリズム、同じである場合は、マルチパートの署名付き MDN メッセージの 2 番目の部分で受信済みのコンテンツ-MIC 拡張フィールドに有効な MIC ダイジェストが含まれていることを確認します。 その場合、MDN が送信されたインターチェンジに対応しない理由を確認します。