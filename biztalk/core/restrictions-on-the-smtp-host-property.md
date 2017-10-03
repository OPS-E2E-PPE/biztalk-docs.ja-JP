---
title: "SMTP ホストのプロパティに関する制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42173fa0ccb01b3ced42965af74e1fcc01d12aba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-on-the-smtp-host-property"></a>SMTP ホストのプロパティに関する制限事項
SMTP ホストのプロパティは、BizTalk Server からメッセージを送信する際に SMTP アダプタによって使用される SMTP サーバーを指定する文字列です。  
  
 このプロパティには、次の規則および制限が適用されます。  
  
-   このプロパティは、アダプタ ハンドラ レベル、エンドポイント レベル、またはその両方の場所で構成する必要があります。  
  
-   SMTP サーバーのプロパティは、次の文字を含めることはできません: ' ~! @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< > /, ?;  
  
-   SMTP サーバー名は 256 文字以内で指定する必要があります。  
  
 SMTP アダプタでは、上記の規則を使用して、デザイン時に常に SMTP ホスト名を検証します。 また、メッセージが SMTP アダプタを使用して動的ポート経由で送信される場合は、実行時に SMTP ホスト名を検証します。  
  
## <a name="see-also"></a>参照  
 [SMTP アダプタの構成時の制限事項](../core/restrictions-when-configuring-the-smtp-adapter.md)