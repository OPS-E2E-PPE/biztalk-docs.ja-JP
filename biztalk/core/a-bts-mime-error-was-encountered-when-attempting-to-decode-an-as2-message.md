---
title: AS2 メッセージをデコードしようとしていますときに BTS MIME エラーが発生しました |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 629e09e950a6c49263230f23725002eee9be905b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985923"
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a>AS2 メッセージをデコードしようとしたときに BTS MIME エラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                         |
| 製品バージョン |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                     |
|    イベント ID     |                                                                 -                                                                  |
|  イベント ソース   |                                                         BizTalk Server EDI                                                         |
|    コンポーネント    |                                                             AS2 エンジン                                                             |
|  シンボル名  |                                                                 -                                                                  |
|  メッセージ テキスト   | AS2 メッセージをデコードしようとしたときに BTS MIME エラーが発生しました。  AS2-から: {0}、AS2-を: {1}、MessageId:{2}エラー。 {3} |
  
## <a name="explanation"></a>説明  
 このエラーが発生するのは、BizTalk MIME コンポーネントを使用して MIME 処理の一部を実行するときです。  
  
## <a name="user-action"></a>ユーザーの操作  
 完全なエラー メッセージでは、MIME コンポーネントで発生した問題について説明します。 (これは、AS2 コンポーネントは MIME 処理の一部の BizTalk MIME コンポーネントを使用するため)、問題の診断の BTS MIME エラー情報を参照してください。