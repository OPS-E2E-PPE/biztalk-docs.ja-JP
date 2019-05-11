---
title: シングル サインオン:イベント 11060 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4851fba-0d3a-4a29-b720-a1d175d20555
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ded0ef8904e0a9def8d02ffe477ef7a3d846c14d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258688"
---
# <a name="single-sign-on-event-11060"></a>シングル サインオン:イベント 11060
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                               エンタープライズ シングル サインオン                                                                                               |
| 製品バージョン |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    イベント ID     |                                                                                                         11060                                                                                                         |
|  イベント ソース   |                                                                                                        ENTSSO                                                                                                         |
|    コンポーネント    |                                                                                                          なし                                                                                                          |
|  シンボル名  |                                                                                            SSO_WARN_PS_MIIS_ACCESS_DENIED                                                                                             |
|  メッセージ テキスト   | MIIS からの Windows パスワード変更は、SSO サービス アカウントからのもののみ受け付けられます。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: % 2 %r<br /><br /> SSO サービス アカウント: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 ENTSSO サーバーが、Microsoft Identity Integration Server (MIIS) からパスワード変更を受け取りました。 しかし、ENTSSO サーバーは、クライアント ユーザー (呼び出し元) が SSO サービス アカウントと同じアカウントの場合にのみ、MIIS からのパスワード変更を受け付けます。  
  
## <a name="user-action"></a>ユーザーの操作  
 MIIS でのパスワード同期の呼び出し元の構成を確認します。 詳細については、次を参照してください。 [MIIS パスワード同期の ENTSSO を構成する方法](../core/how-to-configure-entsso-for-miis-password-sync.md)します。