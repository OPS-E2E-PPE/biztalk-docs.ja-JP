---
title: この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-から |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d338759-5646-4dc2-8319-a42aaa8c3d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5de3b9791c8561f1a2f9e04b2f4915e39454a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394097"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-from"></a>この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-から
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                              InvalidAgreementAS2FromName                               |
|  メッセージ テキスト   |         この AS2 インターチェンジのパーティには、AS2-From の値が含まれている必要があります。          |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージの受信者として解決されるパーティの AS2-From プロパティが設定されていなかったため、送信パイプラインで AS2 メッセージを送信できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、BizTalk Server 管理コンソールを開き、[パーティ] ノードに移動して、メッセージに対して解決されるパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[パーティ - AS2 メッセージの受信者] ノードをクリックし、AS2-From プロパティの値を入力します。