---
title: AS2 EDIINT MIC テーブルにエントリを作成できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1c75d70-e39e-4465-b32b-db646c059c9b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35dd74bc872968b22dd74826e10cb6f23ea24b5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292823"
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a>AS2 EDIINT MIC テーブルにエントリを作成できません。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 製品バージョン |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    イベント ID     |                                                                                       -                                                                                       |
|  イベント ソース   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                             |
|    コンポーネント    |                                                                                  AS2 エンジン                                                                                   |
|  シンボル名  |                                                                        AS2MicDataStoreCreateEntryError                                                                        |
|  メッセージ テキスト   | AS2 EDIINT MIC テーブルにエントリを作成できません。 これは、重複する AS2 によって発生する可能性があります、AS2 から-をおよび MessageID の組み合わせ、テーブルに書き込まれています。  エラー: {0} |
  
## <a name="explanation"></a>説明  
 このエラーは、データベース接続の問題またはデータベース テーブルのキーが既に存在する行のいずれかを示します。 完全なエラー メッセージは、挿入操作が失敗した理由に関する情報を提供する必要があります。 MDN の受信後に (成功または失敗) かどうか、MDN が受信された後、このエラーは発生しないように、テーブル内のエントリが削除されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、挿入操作が失敗した理由については、完全なエラー メッセージを確認します。 SQL では、EDIINT_MIC テーブル内かどうかが確認重複する AS2-からおよび AS2 の MessageID の組み合わせ。 そうである場合は、それらを削除します。