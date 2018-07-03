---
title: 認証エラーが発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36524da9-da91-41e7-bf73-7781cde20c80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5548d448d2c0d45addc72639ad229cf4ee1bf37f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022352"
---
# <a name="there-was-an-authentication-failure"></a>認証エラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
| 製品バージョン |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                     |
|    イベント ID     |                                                                                                 -                                                                                                 |
|  イベント ソース   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                       |
|    コンポーネント    |                                                                                            EDI エンジン                                                                                             |
|  シンボル名  |                                                                                         DescPartyNotFound                                                                                         |
|  メッセージ テキスト   | 認証エラーが発生しました。 処理中のメッセージに一致するパーティが存在することを確認してください。 存在する場合、メッセージ内のセキュリティ/パスワード情報がパーティの構成と一致します。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server がメッセージの送信者を認証できなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   インターチェンジ ヘッダーの中の送信者の修飾子と識別子 (X12 の場合は ISA5 と ISA6、EDIFACT の場合は UNB2.1 と UNB2.2 の各フィールド) が、パーティのプロパティに含まれる送信者の修飾子と識別子 ([EDI のプロパティ] ダイアログ ボックスの [インターチェンジ処理のプロパティ] ページで定義された) に一致することを確認します。  
  
-   インターチェンジのヘッダー中のセキュリティ/パスワード情報 (X12 の場合は ISA3 と ISA4、EDIFACT の場合は UNB6.1 と UNB6.2 の各フィールド) が、パーティのプロパティに含まれるセキュリティ/パスワード情報 ([EDI のプロパティ] ダイアログ ボックスの [インターチェンジ処理のプロパティ] ページで定義された) に一致することを確認します。