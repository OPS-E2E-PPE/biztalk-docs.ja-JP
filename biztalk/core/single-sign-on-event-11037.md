---
title: シングル サインオン:イベント 11037 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d64605fbdd4cb470fc6dec060650bd78b581f84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401030"
---
# <a name="single-sign-on-event-11037"></a>シングル サインオン:イベント 11037
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                               エンタープライズ シングル サインオン                                                                                                               |
| 製品バージョン |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    イベント ID     |                                                                                                                         11037                                                                                                                         |
|  イベント ソース   |                                                                                                                        ENTSSO                                                                                                                         |
|    コンポーネント    |                                                                                                                          なし                                                                                                                          |
|  シンボル名  |                                                                                                              SSO_INFO_PS_MAPPING_INVALID                                                                                                              |
|  メッセージ テキスト   | 外部パスワード変更。 マッピングが valid.%r ではなくなったため、外部アカウントのパスワードが変更されませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |
  
## <a name="explanation"></a>説明  
 マッピングは、アプリケーション ユーザー グループの一部ではなくなりました。  
  
## <a name="user-action"></a>ユーザーの操作  
 メッセージには、外部アカウントとアプリケーションの名前が一覧表示します。 この情報を使用して、理由、マッピングが無効になったを確認することができます。