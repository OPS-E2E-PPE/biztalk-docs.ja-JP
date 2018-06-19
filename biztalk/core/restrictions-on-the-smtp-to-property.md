---
title: SMTP の To プロパティに関する制限事項 |Microsoft ドキュメント
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
ms.openlocfilehash: b59495ac94b3591801101607533eb9c7dba158fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268338"
---
# <a name="restrictions-on-the-smtp-to-property"></a>SMTP の To プロパティに関する制限事項
**に**プロパティは、メッセージの受信者の SMTP アドレスを指定する文字列。 SMTP サーバーでサポートされている区切り記号を使用して、複数のアドレスを指定できます。  
  
 SMTP アドレスの形式に固有の制限はありません。 したがって、アダプタは SMTP サーバーでサポートされているすべての形式を受け入れます。 ユーザーが有効でないアドレスを指定すると、送信操作は失敗し、SMTP 送信アダプタによってエラーが報告されます。  
  
 このプロパティの唯一の制限は、プロパティが空でなく、サイズが 256 文字を超えないようにする必要があることです。  
  
## <a name="see-also"></a>参照  
 [SMTP アダプタの構成時の制限事項](../core/restrictions-when-configuring-the-smtp-adapter.md)