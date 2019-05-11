---
title: シングル サインオン:イベント 10603 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139d1eb5-af88-4216-9604-c052f3db13c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c57b75ba39be2b49606b351573f50c677077aa48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397780"
---
# <a name="single-sign-on-event-10603"></a>シングル サインオン:イベント 10603
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                             エンタープライズ シングル サインオン                                                              |
| 製品バージョン |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    イベント ID     |                                                                       10603                                                                        |
|  イベント ソース   |                                                                       ENTSSO                                                                       |
|    コンポーネント    |                                                                        なし                                                                         |
|  シンボル名  |                                                                 SSO_WARN_DB_ACCESS                                                                 |
|  メッセージ テキスト   | SSO データベースにアクセスできませんでした。 この条件が解決しない場合、SSO サービスになる offline.%r<br /><br /> %1.%r<br /><br /> SQL エラー コード: %2 |
  
## <a name="explanation"></a>説明  
 SSO データベースは使用できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告に含まれる SQL エラー コードを確認します。 いくつかのガイダンスが提供することができます。 それ以外の場合は、マイクロソフト製品サポート サービスにお問い合わせください。