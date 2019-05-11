---
title: シングル サインオン:イベント 10610 |Microsoft Docs
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
ms.openlocfilehash: 451468316420c0653b967a25f233564303a6e1a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397724"
---
# <a name="single-sign-on-event-10610"></a>シングル サインオン:イベント 10610
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                       エンタープライズ シングル サインオン                                                       |
| 製品バージョン |                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    イベント ID     |                                                                 10610                                                                 |
|  イベント ソース   |                                                                ENTSSO                                                                 |
|    コンポーネント    |                                                                  なし                                                                  |
|  シンボル名  |                                                      SSO_WARN_CRED_CACHE_FAILED                                                       |
|  メッセージ テキスト   | 資格情報のキャッシュでは、予期しないエラーが発生し、シャット ダウンします。 Performance.%r に影響する可能性があります。<br /><br /> エラー コード: %1 |
  
## <a name="explanation"></a>説明  
 資格情報のキャッシュでは、予期しないエラーが発生し、シャット ダウンします。 これは、パフォーマンスに影響を与える、機能は影響しません。  
  
## <a name="user-action"></a>ユーザーの操作  
 適切なときに、SSO サービスを再起動します。