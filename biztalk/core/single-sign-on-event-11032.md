---
title: シングル サインオン:イベント 11032 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d58cf9d-6806-4580-8014-7eff88d5cc5f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 376a7350aee5805a99563d7eba548651fd87ffc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401797"
---
# <a name="single-sign-on-event-11032"></a>シングル サインオン:イベント 11032
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                            エンタープライズ シングル サインオン                                                                                                                             |
| 製品バージョン |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    イベント ID     |                                                                                                                                      11032                                                                                                                                       |
|  イベント ソース   |                                                                                                                                      ENTSSO                                                                                                                                      |
|    コンポーネント    |                                                                                                                                       なし                                                                                                                                        |
|  シンボル名  |                                                                                                                     SSO_INFO_PS_WIN_CHANGE_MAPPING_DISABLED                                                                                                                      |
|  メッセージ テキスト   | Windows パスワードが変更されています。 この Windows アカウントのマッピングが検出されましたが disabled.%r であるために無視されました<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーションの場合: % 3 %r<br /><br /> 外部アカウント: % 4 %r<br /><br /> クライアント ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 この Windows アカウントのマッピングが検出されましたが、無効になっているため、無視されます。  
  
## <a name="user-action"></a>ユーザーの操作  
  
-   マッピングを有効にするのを参照してください。[ユーザー マッピングを有効にする方法](../core/how-to-enable-a-user-mapping.md)します。