---
title: 失敗の制御番号のリセット |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e83c07-1569-4433-b882-a26784b7bb0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 480a61535697d0b04fa106b4f7930a8a54362e0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996603"
---
# <a name="reset-for-control-number-failed"></a>制御番号のリセットが失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                              EdiControlNumberResetFailed                               |
|  メッセージ テキスト   |                                 リセット{0}できませんでした。                                  |
  
 **{0}**: トランザクション セット制御番号/グループ制御番号/インターチェンジ制御番号  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server が制御番号をリセットできなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、UI を再び開いてやり直してください。