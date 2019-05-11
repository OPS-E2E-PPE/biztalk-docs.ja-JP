---
title: シングル サインオン:イベント 11069 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1accfe68-000c-4b5e-909c-244e18eba110
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc680a452c6e70f6e10623779da1ca312f62a1fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396078"
---
# <a name="single-sign-on-event-11069"></a>シングル サインオン:イベント 11069
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                               エンタープライズ シングル サインオン                                                                                               |
| 製品バージョン |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    イベント ID     |                                                                                                         11069                                                                                                         |
|  イベント ソース   |                                                                                                        ENTSSO                                                                                                         |
|    コンポーネント    |                                                                                                          なし                                                                                                          |
|  シンボル名  |                                                                                             SSO_WARN_PS_PCNS_NOT_ALLOWED                                                                                              |
|  メッセージ テキスト   | 現在、この SSO サーバーでは、PCNS からの Windows パスワード変更ができないように構成されています。 'ssoconfig -allowPS PCNS yes' または SSO 管理 MMC を使用します。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2 |
  
## <a name="explanation"></a>説明  
 現在、この SSO サーバーでは、PCNS からの Windows パスワード変更ができないように構成されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 PCNS からの Windows パスワードの変更を許可する、**サーバー スナップイン**、**パスワード同期プロパティ**] タブで [ **PCNS からのパスワード同期を許可します。**  
  
 詳細については、次を参照してください。[サーバー スナップインを使用する](../core/how-to-use-the-servers-snap-in.md)します。