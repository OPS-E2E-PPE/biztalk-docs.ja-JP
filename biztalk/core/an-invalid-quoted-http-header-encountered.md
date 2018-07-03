---
title: 無効な HTTP ヘッダーが検出されました引用符で囲まれた |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb530ee6-ec6a-4791-ae99-b9db426c0896
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ca0d7463f4604e8a159c12fab690e494a13fb60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971011"
---
# <a name="an-invalid-quoted-http-header-encountered"></a>引用符で囲まれた無効な HTTP ヘッダーが検出されました
## <a name="details"></a>詳細  
  
|                 |                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------|
|  製品名   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| 製品バージョン |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                          |
|    イベント ID     |                                                      -                                                       |
|  イベント ソース   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI            |
|    コンポーネント    |                                                  AS2 エンジン                                                  |
|  シンボル名  |                                                      -                                                       |
|  メッセージ テキスト   | 引用符で囲まれた無効な HTTP ヘッダーが検出されました。  詳細については次のとおり: ヘッダー名:"{0}"ヘッダーの値:"{1}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージの AS2-From または AS2-To HTTP ヘッダーの名前が正しく引用符で囲まれていなかったため、AS2 受信パイプラインまたは AS2 送信パイプラインで AS2 メッセージを処理できなかったことを示します。 ヘッダー名は、名前内でスペース、バックスラッシュ、または二重引用符に対応するために、引用符で囲みます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、RFC 4130「MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」のセクション 6.2「AS2 System Identifiers」に記載されているルールに従って、AS2 メッセージのヘッダー名を引用符で囲みます。