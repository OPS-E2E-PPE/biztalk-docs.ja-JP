---
title: 'シングル サインオン: イベント 10574 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f2a5aa-3a19-4d7c-9257-89f1567a3c2d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be3700f565dafb9003a3cc05d9e52c7559904f88
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976955"
---
# <a name="single-sign-on-event-10574"></a>シングル サインオン: イベント 10574
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                        エンタープライズ シングル サインオン                                                                         |
| 製品バージョン |                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                        |
|    イベント ID     |                                                                                  10574                                                                                   |
|  イベント ソース   |                                                                                  ENTSSO                                                                                  |
|    コンポーネント    |                                                                                   なし                                                                                    |
|  シンボル名  |                                                                     SSO_WARN_INVALID_SSO_ADMIN_GROUP                                                                     |
|  メッセージ テキスト   | SSO 管理者アカウントがグローバル情報の更新について有効ではありません。%r<br /><br /> SSO 管理者: % 1 %r<br /><br /> 無効なアカウント: % 2 %r<br /><br /> エラー コード: %3 |
  
## <a name="explanation"></a>説明  
 SSO 管理者アカウントがグローバル情報の更新について有効ではありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告メッセージには、SSO 管理者アカウントおよび無効なアカウントに関する情報が含まれています。 この情報を確認し、必要に応じて修正を行い、もう一度更新を試行します。