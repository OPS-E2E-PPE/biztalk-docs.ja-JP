---
title: 無効な AS2 の処理中に検出名 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84d848b5-b2a3-460d-85d4-c3576e4e3aaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf17c8221686562ec6cc74578d646bb832d4ea22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330916"
---
# <a name="invalid-as2-to-name-encountered-during-processing"></a>無効な AS2 の処理中に検出名
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                            InvalidAS2ToNameEncounteredError                            |
|  メッセージ テキスト   |             無効な AS2 の処理中に発生する名前にします。  値: {0}             |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントまたはを示します、受信パイプラインで受信インターチェンジを処理できなかったために、送信パイプラインは、送信インターチェンジを処理できませんでした、AS2 の値のヘッダーに準拠しないと、AS2 RFC 4130 の仕様。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決することを確認、AS2 の受信または送信メッセージのメッセージ ヘッダーには、AS2 RFC 4130 のセクション 6.2 の仕様に準拠しています。