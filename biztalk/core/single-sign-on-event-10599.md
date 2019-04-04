---
title: 'シングル サインオン: イベント 10599 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd671aa5-b243-4081-9a4e-87103be9a1d7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 326b94be9c05be6645a21b10f3ea302cf63be8e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015683"
---
# <a name="single-sign-on-event-10599"></a>シングル サインオン: イベント 10599
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                             エンタープライズ シングル サインオン                                                                              |
| 製品バージョン |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    イベント ID     |                                                                                       10599                                                                                        |
|  イベント ソース   |                                                                                       ENTSSO                                                                                       |
|    コンポーネント    |                                                                                        なし                                                                                         |
|  シンボル名  |                                                                              SSO_WARN_ENTSSO_IS_ADMIN                                                                              |
|  メッセージ テキスト   | SSO サービスはローカル管理者アカウントで実行しています。 これは、セキュリティ上の理由により推奨されていません。 Details.%r のドキュメントを参照してください。<br /><br /> SSO サービス アカウント: %1 |
  
## <a name="explanation"></a>説明  
 指定された SSO サービスはローカル管理者アカウントで実行しています。 これは、セキュリティ上の理由により推奨されていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 詳細については、[SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)を参照してください。