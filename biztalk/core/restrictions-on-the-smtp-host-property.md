---
title: SMTP ホストのプロパティに関する制限事項 |Microsoft ドキュメント
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
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 465946f15d11f087995b8000231796c5e204c077
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972904"
---
# <a name="restrictions-on-the-smtp-host-property"></a>SMTP ホストのプロパティに関する制限事項
SMTP ホストのプロパティは、BizTalk Server からメッセージを送信する際に SMTP アダプタによって使用される SMTP サーバーを指定する文字列です。  
  
 このプロパティには、次の規則および制限が適用されます。  
  
-   このプロパティは、アダプタ ハンドラ レベル、エンドポイント レベル、またはその両方の場所で構成する必要があります。  
  
-   SMTP サーバーのプロパティは、次の文字を含めることはできません: ' ~! @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;  
  
-   SMTP サーバー名は 256 文字以内で指定する必要があります。  
  
 SMTP アダプタでは、上記の規則を使用して、デザイン時に常に SMTP ホスト名を検証します。 また、メッセージが SMTP アダプタを使用して動的ポート経由で送信される場合は、実行時に SMTP ホスト名を検証します。  
  
## <a name="see-also"></a>参照  
 [SMTP アダプター構成時の制限事項](../core/restrictions-when-configuring-the-smtp-adapter.md)