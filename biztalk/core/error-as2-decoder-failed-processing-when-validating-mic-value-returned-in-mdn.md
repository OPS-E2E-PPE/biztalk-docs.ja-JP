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
ms.openlocfilehash: 2b15ec1518e4736052e31254283db66395d87fb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985843"
---
# <a name="the-as2-decoder-failed-processing-when-validating-the-mic-value-returned-in-the-mdn"></a>AS2 デコーダーで、MDN に返された MIC 値の検証中に処理が失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| 製品バージョン |                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    イベント ID     |                                                                                                   -                                                                                                   |
|  イベント ソース   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                         |
|    コンポーネント    |                                                                                              AS2 エンジン                                                                                               |
|  シンボル名  |                                                                                AS2DecoderMdnMicFailureDuringProcessing                                                                                |
|  メッセージ テキスト   | AS2 デコーダで、MDN に返された MIC 値の検証中に処理が失敗しました。  MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、MIC (メッセージ整合性チェック) の検証が失敗したため、受信パイプラインで受信 MDN を処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、MDN の生成に使用されるアルゴリズム (元のメッセージの Signed-Receipt-MICalg ヘッダー) が、AS2 メッセージの受信者の Signed-Receipt-MICalg プロパティで指定されているアルゴリズムと同じであることを確認します。 両方が SHA1 または MD5 のどちらかである必要があります。 指定されているアルゴリズムが同じである場合は、マルチパートの署名付き MDN メッセージの 2 番目の部分にある Received-Content-MIC 拡張フィールドに、有効な MIC ダイジェストが含まれていることを確認します。 有効な MIC ダイジェストが含まれている場合は、送信されたインターチェンジに MDN が対応していない理由を特定します。