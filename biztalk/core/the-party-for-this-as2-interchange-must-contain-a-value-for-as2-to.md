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
ms.openlocfilehash: 333657b16b0e4a0b9bbbb30c73641f7db8466b87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006699"
---
# <a name="the-party-for-this-as2-interchange-must-contain-a-value-for-as2-to"></a>この AS2 インターチェンジのパーティには、AS2-To の値が含まれている必要があります
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                               InvalidAgreementAS2ToName                                |
|  メッセージ テキスト   |          この AS2 インターチェンジのパーティには、AS2-To の値が含まれている必要があります。           |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージの受信者として解決されるパーティの AS2-To プロパティが設定されていなかったため、送信パイプラインで送信 AS2 メッセージを処理できなかったことを示します。 これは、送信 AS2 メッセージのパーティが、パーティに関連付けられた送信ポートとメッセージをサブスクライブした送信ポートの照合によって解決されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように操作を行います。  
  
1.  BizTalk Server 管理コンソールを開きます。  
  
2.  [パーティ] ノードに移動し、メッセージに関して解決されるパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。  
  
3.  [パーティ - AS2 メッセージの受信者] ノードをクリックします。  
  
4.  AS2-To プロパティの値を入力します。