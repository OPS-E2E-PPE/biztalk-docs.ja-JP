---
title: 'シングル サインオン: イベント 10601 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ea1dfbcc36cc83498aa316cedeab8fc46a2f4dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987739"
---
# <a name="single-sign-on-event-10601"></a>シングル サインオン: イベント 10601
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                  エンタープライズ シングル サインオン                                                                                                                   |
| 製品バージョン |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    イベント ID     |                                                                                                                            10601                                                                                                                             |
|  イベント ソース   |                                                                                                                            ENTSSO                                                                                                                            |
|    コンポーネント    |                                                                                                                             なし                                                                                                                              |
|  シンボル名  |                                                                                                                    SSO_WARN_INVALID_FLAGS                                                                                                                    |
|  メッセージ テキスト   | 指定されたフラグはこの種類のアプリケーションの作成には無効です。<br /><br /> Details.%r のドキュメントを参照してください。<br /><br /> アプリケーション名: %1 %r<br /><br /> 指定したフラグ: % 2 %r<br /><br /> 許可されているフラグ: % 3 %r<br /><br /> 許可されていないフラグ: %4 |
  
## <a name="explanation"></a>説明  
 指定されたフラグはこの種類のアプリケーションの作成には無効です。 この警告には、関連するアプリケーションと共に、許可されているフラグと許可されていないフラグが示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告メッセージに示されているガイドラインに従ってアプリケーションを再作成します。