---
title: SMTP ホストのプロパティに関する制限事項 |Microsoft Docs
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
ms.openlocfilehash: 60eee7ce4acb940d2d0011ead80bdcf9c5ed335c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254885"
---
# <a name="restrictions-on-the-smtp-host-property"></a>SMTP ホストのプロパティに関する制限事項
SMTP ホストのプロパティは、BizTalk server からメッセージを送信する SMTP アダプタを使用する SMTP サーバーを指定する文字列です。  
  
 このプロパティには、次の規則と制限事項が適用されます。  
  
- このプロパティは、エンドポイント レベルで、または両方の場所のアダプタ ハンドラ レベルで構成する必要があります。  
  
- SMTP サーバーのプロパティは、次の文字を含めることはできません ' ~!。 @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;  
  
- SMTP サーバー名の長さは 256 文字を超えない必要があります。  
  
  SMTP アダプターは常に、前述の規則を使用して、デザイン時に SMTP ホスト名を検証します。 さらに、SMTP アダプタは、SMTP アダプターで動的ポート経由でメッセージが送信される場合、実行時に SMTP ホスト名を検証します。  
  
## <a name="see-also"></a>参照  
 [SMTP アダプター構成時の制限事項](../core/restrictions-when-configuring-the-smtp-adapter.md)