---
title: シングル サインオン:イベント 10575 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a691812-433c-42ba-a225-873ad1bfee99
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76cd29d85b700eadb0bce35822a2ab73493755c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295928"
---
# <a name="single-sign-on-event-10575"></a>シングル サインオン:イベント 10575
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                     エンタープライズ シングル サインオン                                                                                     |
| 製品バージョン |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    イベント ID     |                                                                                               10575                                                                                               |
|  イベント ソース   |                                                                                              ENTSSO                                                                                               |
|    コンポーネント    |                                                                                                なし                                                                                                |
|  シンボル名  |                                                                                  SSO_INFO_CHANGED_SECRET_SERVER                                                                                   |
|  メッセージ テキスト   | シークレット サーバー name.%r の更新<br /><br /> 新しいシークレット サーバー: % 1 %r<br /><br /> 古いシークレット サーバー: % 2 %r<br /><br /> 追跡 ID: % 3 %r<br /><br /> クライアント コンピューターの場合: % 4 %r<br /><br /> クライアント ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 これは、情報メッセージであり、SSO システム内でその発生の重要なセキュリティ関連イベントを追跡するために便利です。 このメッセージは、シークレット サーバー名が更新されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーによる操作は不要です。