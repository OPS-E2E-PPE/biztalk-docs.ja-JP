---
title: 'シングル サインオン: イベント 10843 |Microsoft Docs'
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
ms.openlocfilehash: 40b7e03f54d4c4ac2b7074d2aa13d771ce20a9e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013003"
---
# <a name="single-sign-on-event-10843"></a>シングル サインオン: イベント 10843
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                      エンタープライズ シングル サインオン                                                                      |
| 製品バージョン |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    イベント ID     |                                                                                10843                                                                                |
|  イベント ソース   |                                                                               ENTSSO                                                                                |
|    コンポーネント    |                                                                                 なし                                                                                 |
|  シンボル名  |                                                                         ENTSSO_E_NO_SECRET2                                                                         |
|  メッセージ テキスト   | マスター シークレット サーバーからシークレットを入手できないため、暗号化または解読を実行できません。 イベント ログ (コンピューター '%1' 上) で関連エラーを参照してください。 |
  
## <a name="explanation"></a>説明  
 アクセスが拒否されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 マスター シークレット サーバーがオフライン状態、またはいずれか、マスター シークレット サーバーに必要なマスター シークレットがありません。 指定されたコンピューター上のイベント ログで関連エラーを参照します。