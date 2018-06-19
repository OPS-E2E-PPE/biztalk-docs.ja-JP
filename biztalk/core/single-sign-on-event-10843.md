---
title: 'シングル サインオン: イベント 10843 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd86a39d515858e1cda09317ba6139bc67c95ed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276274"
---
# <a name="single-sign-on-event-10843"></a>シングル サインオン: イベント 10843
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10843|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_NO_SECRET2|  
|メッセージ テキスト|マスター シークレット サーバーからシークレットを入手できないため、暗号化または解読を実行できません。 イベント ログ (コンピューター '%1' 上) で関連エラーを参照してください。|  
  
## <a name="explanation"></a>説明  
 アクセスが拒否されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 マスター シークレット サーバーがオフライン、または、マスター シークレット サーバーに必要なマスター シークレットがありません。 指定されたコンピューター上のイベント ログで関連エラーを参照します。