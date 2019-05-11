---
title: シングル サインオン:イベント 10843 |Microsoft Docs
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
ms.openlocfilehash: 8389a1b6443fbe2d4abe592b305508b2780afdf6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307314"
---
# <a name="single-sign-on-event-10843"></a>シングル サインオン:イベント 10843
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                      エンタープライズ シングル サインオン                                                                      |
| 製品バージョン |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    イベント ID     |                                                                                10843                                                                                |
|  イベント ソース   |                                                                               ENTSSO                                                                                |
|    コンポーネント    |                                                                                 なし                                                                                 |
|  シンボル名  |                                                                         ENTSSO_E_NO_SECRET2                                                                         |
|  メッセージ テキスト   | シークレットがマスター シークレット サーバーから利用できないために、暗号化または復号化を実行できません。 関連するエラーについては、(コンピュータ '%1') のイベント ログを参照してください。 |
  
## <a name="explanation"></a>説明  
 アクセスが拒否されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 マスター シークレット サーバーがオフライン状態、またはいずれか、マスター シークレット サーバーに必要なマスター シークレットがありません。 関連するエラーの指定したコンピューター上のイベント ログを参照してください。