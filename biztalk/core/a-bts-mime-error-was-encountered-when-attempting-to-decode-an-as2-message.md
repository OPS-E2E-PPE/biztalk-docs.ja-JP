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
ms.openlocfilehash: 411359b55fff0385cdda5ae52a9c59477526ccb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362458"
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a>AS2 メッセージをデコードしようとしています。 ときに BTS MIME エラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                         |
| 製品バージョン |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                     |
|    イベント ID     |                                                                 -                                                                  |
|  イベント ソース   |                                                         BizTalk Server EDI                                                         |
|    コンポーネント    |                                                             AS2 エンジン                                                             |
|  シンボル名  |                                                                 -                                                                  |
|  メッセージ テキスト   | AS2 メッセージをデコードしようとしています。 BTS MIME エラーが発生しました。  AS2-から: {0}、AS2-を: {1}、MessageId:{2}エラー。 {3} |
  
## <a name="explanation"></a>説明  
 BizTalk MIME コンポーネントを使用して、MIME 処理の一部を処理する場合は、このエラーが発生しました。  
  
## <a name="user-action"></a>ユーザーの操作  
 完全なエラー メッセージでは、MIME コンポーネントで発生した問題について説明します。 (これは、AS2 コンポーネントは MIME 処理の一部の BizTalk MIME コンポーネントを使用するため)、問題の診断の BTS MIME エラー情報を参照してください。