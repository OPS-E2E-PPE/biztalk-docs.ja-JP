---
title: シングル サインオン:イベント 10601 |Microsoft Docs
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
ms.openlocfilehash: dedc94aa8cb5881e4ef738f6414f51463684003a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397789"
---
# <a name="single-sign-on-event-10601"></a>シングル サインオン:イベント 10601
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                  エンタープライズ シングル サインオン                                                                                                                   |
| 製品バージョン |                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                  |
|    イベント ID     |                                                                                                                            10601                                                                                                                             |
|  イベント ソース   |                                                                                                                            ENTSSO                                                                                                                            |
|    コンポーネント    |                                                                                                                             なし                                                                                                                              |
|  シンボル名  |                                                                                                                    SSO_WARN_INVALID_FLAGS                                                                                                                    |
|  メッセージ テキスト   | 指定したフラグは、この種類のアプリケーションを作成できません。<br /><br /> Details.%r のドキュメントを参照してください。<br /><br /> アプリケーション名: %1 %r<br /><br /> 指定したフラグ: % 2 %r<br /><br /> 許可されているフラグ: % 3 %r<br /><br /> 許可されていないフラグ: %4 |
  
## <a name="explanation"></a>説明  
 指定したフラグは、この種類のアプリケーションを作成できません。 警告には、関連するアプリケーションだけでなくは許可されているフラグといないものが一覧表示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告メッセージに記載されているガイドラインに従うアプリケーションを再作成します。