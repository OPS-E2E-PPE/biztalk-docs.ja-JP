---
title: 'シングル サインオン: イベント 10563 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49fc95cf7c257febd6ab631dcc016598dd2e4e24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976506"
---
# <a name="single-sign-on-event-10563"></a>シングル サインオン: イベント 10563
## <a name="details"></a>詳細  
  
|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  製品名   |                      エンタープライズ シングル サインオン                       |
| 製品バージョン |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    イベント ID     |                                10563                                 |
|  イベント ソース   |                                ENTSSO                                |
|    コンポーネント    |                                 なし                                  |
|  シンボル名  |                       SSO_WARN_PERFMON_FAILED                        |
|  メッセージ テキスト   | パフォーマンス監視を開始できませんでした。%r<br /><br /> エラー コード: %1 |
  
## <a name="explanation"></a>説明  
 パフォーマンス監視を開始できませんでした。 システムは通常の実行を続行できますが、パフォーマンス監視は使用できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 perfmon ユーティリティのアンインストールと再インストールが必要である可能性があります。