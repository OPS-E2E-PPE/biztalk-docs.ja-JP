---
title: SMTP の To プロパティに関する制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: c876d30e-44ab-462d-8c98-64416ed6dd1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f75539b7bcd9feb1e66695361a1a208b12eda812
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399110"
---
# <a name="restrictions-on-the-smtp-to-property"></a>SMTP の To プロパティに関する制限事項
**に**プロパティは、メッセージの受信者の SMTP アドレスを指定する文字列です。 SMTP サーバーがサポートする区切り記号では、いくつかのアドレスを一覧表示できます。  
  
 SMTP アドレスの形式については、特定の制限はありません。 これは、アダプターが SMTP サーバーをサポートする任意の形式を受け入れることを意味します。 ユーザーは、無効なアドレスを提供する場合は、送信操作は失敗し、SMTP 送信アダプターはエラーを報告します。  
  
 このプロパティの唯一の制限は、空を認めないし、そのサイズは 256 文字を超えないことです。  
  
## <a name="see-also"></a>参照  
 [SMTP アダプター構成時の制限事項](../core/restrictions-when-configuring-the-smtp-adapter.md)