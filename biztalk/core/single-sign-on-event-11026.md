---
title: シングル サインオン:イベント 11026 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e39b252d-2ed0-4006-aac2-4dce6504afb2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9443afe9fd9101d5ede8e5e05adfc6f65d877c90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379980"
---
# <a name="single-sign-on-event-11026"></a>シングル サインオン:イベント 11026
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                エンタープライズ シングル サインオン                                                                                                                                |
| 製品バージョン |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    イベント ID     |                                                                                                                                          11026                                                                                                                                          |
|  イベント ソース   |                                                                                                                                         ENTSSO                                                                                                                                          |
|    コンポーネント    |                                                                                                                                           なし                                                                                                                                           |
|  シンボル名  |                                                                                                                             SSO_WARN_EXISTING_GROUP_MAPPING                                                                                                                             |
|  メッセージ テキスト   | 既存のマッピングとの競合があるために、新しいグループ マッピングを作成できませんでした。 既存のマッピングを削除してやり直してください again.%r<br /><br /> 既存のマッピング: % 1 %r<br /><br /> 新しいマッピング: % 2 %r<br /><br /> 外部アカウント: % 3 %r<br /><br /> アプリケーション名: %4 |
  
## <a name="explanation"></a>説明  
 最も一般的な原因は、システムがエンタープライズ シングル サインオン、および古いグループ アプリケーションの古いバージョンを使用しています。  
  
## <a name="user-action"></a>ユーザーの操作  
 削除し、警告で指摘されているように、マッピングを再作成します。 これに失敗した場合は、エンタープライズ シングル サインオンのより新しいバージョンにアップグレードする必要があります。