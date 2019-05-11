---
title: この AS2 インターチェンジのパーティが AS2 の値を含める必要がありますを |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 029eae5d-4c13-402d-90c5-8e9ef3814a1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccabce0ce60f018f6d55d64a26c1f9540ed88fa2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394104"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a>この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-を
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                               InvalidAgreementAS2ToName                                |
|  メッセージ テキスト   |          この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-にします。           |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、エントリのため、送信パイプラインが送信 AS2 メッセージが処理しないことを示します、AS2 のプロパティにはメッセージの受信者として解決されるパーティは設定されませんでした。 これは、送信 AS2 メッセージのパーティがメッセージにサブスクライブする送信ポートとパーティに関連付けられている送信ポートを照合することによって解決されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように操作を行います。  
  
1.  BizTalk Server 管理コンソールを開きます。  
  
2.  パーティ ノードに移動し、メッセージに対して解決されるパーティの AS2 のプロパティ ダイアログ ボックスを開きます。  
  
3.  AS2 メッセージの受信者 ノードには、パーティをクリックします。  
  
4.  AS2 の値を入力、プロパティにします。