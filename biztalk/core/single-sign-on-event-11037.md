---
title: 'シングル サインオン: イベント 11037 |Microsoft Docs'
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
ms.openlocfilehash: ceec837a53d4cad3c236373a907497795efbd12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998899"
---
# <a name="single-sign-on-event-11037"></a>シングル サインオン: イベント 11037
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                               エンタープライズ シングル サインオン                                                                                                               |
| 製品バージョン |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    イベント ID     |                                                                                                                         11037                                                                                                                         |
|  イベント ソース   |                                                                                                                        ENTSSO                                                                                                                         |
|    コンポーネント    |                                                                                                                          なし                                                                                                                          |
|  シンボル名  |                                                                                                              SSO_INFO_PS_MAPPING_INVALID                                                                                                              |
|  メッセージ テキスト   | 外部パスワードが変更されています。 マッピングが有効ではなくなっているため、外部アカウントのパスワードは変更されませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: %4 |
  
## <a name="explanation"></a>説明  
 マッピングがアプリケーション ユーザー グループに含まれなくなっています。  
  
## <a name="user-action"></a>ユーザーの操作  
 このメッセージには、外部アカウントとアプリケーションの名前が示されます。 この情報を使用して、マッピングが有効ではなくなった理由を調べます。