---
title: 'シングル サインオン: イベント 10610 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c90855c1f136dc8204afe718ea4456c834ab667
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024408"
---
# <a name="single-sign-on-event-10610"></a>シングル サインオン: イベント 10610
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                       エンタープライズ シングル サインオン                                                       |
| 製品バージョン |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    イベント ID     |                                                                 10610                                                                 |
|  イベント ソース   |                                                                ENTSSO                                                                 |
|    コンポーネント    |                                                                  なし                                                                  |
|  シンボル名  |                                                      SSO_WARN_CRED_CACHE_FAILED                                                       |
|  メッセージ テキスト   | 資格情報キャッシュに予期しないエラーが発生し、シャットダウンされました。 パフォーマンスが低下する場合があります。%r<br /><br /> エラー コード: %1 |
  
## <a name="explanation"></a>説明  
 資格情報キャッシュに予期しないエラーが発生し、シャットダウンされました。 これによってパフォーマンスは低下する場合がありますが、機能への影響はありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 適切なときに SSO サービスを再起動します。