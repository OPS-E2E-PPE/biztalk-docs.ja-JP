---
title: シングル サインオン:イベント 10611 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b0e07a7d3151cf4a25334d1d6b01fb46c3ad75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397717"
---
# <a name="single-sign-on-event-10611"></a>シングル サインオン:イベント 10611
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                         エンタープライズ シングル サインオン                                                                                                         |
| 製品バージョン |                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    イベント ID     |                                                                                                                   10611                                                                                                                   |
|  イベント ソース   |                                                                                                                  ENTSSO                                                                                                                   |
|    コンポーネント    |                                                                                                                    なし                                                                                                                    |
|  シンボル名  |                                                                                                     SSO_INFO_SERVICE_STARTING_NO_SSL                                                                                                      |
|  メッセージ テキスト   | SSO サービスが starting.%r<br /><br /> コンピューター名: %1 %r<br /><br /> SQL Server 名: % 2 %r<br /><br /> SSO データベース名: % 3 %r<br /><br /> SSL を使用していません。 SQL Server の接続をセキュリティで保護する方法の詳細についてはドキュメントを参照してください。 |
  
## <a name="explanation"></a>説明  
 ENTSSO サービスは、Secure Sockets Layer (SSL) を使用しないで起動しています。 To SQL、SSO サービスからの接続を保護することをお勧めします。  
  
## <a name="user-action"></a>ユーザーの操作  
 ドキュメントを参照[SSO の SSL を有効にする方法](../core/how-to-enable-ssl-for-sso.md)  
  
 .