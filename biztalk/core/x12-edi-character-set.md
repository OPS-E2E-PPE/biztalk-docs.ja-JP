---
title: "X12 EDI 文字セット |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bcf25317d38846c6376b1fa25572b926c92992
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="x12-edi-character-set"></a>X12 EDI 文字セット
Ñ 文字または抑音アクセント (') を使用する場合は、次のことを指定します。  
  
||文字セット|  
|-|-------------------|  
|EDI ドキュメント内の Ñ 文字のみ|拡張文字セットを使用します|  
|EDI ドキュメント内の抑音アクセント (`) のみ|UTF8 文字セットの使用|  
|Ñ 文字**と**同じドキュメント内の抑音アクセント (')。|UTF8 エンコード-受信ドキュメントである必要があります。<br />-UTF8 文字セットを使用します。|  
  
 EDI 文字セットの詳細については、次のリンクを参照してください。  
  
 [EDI 文字セット](http://go.microsoft.com/fwlink/p/?LinkId=271249)  
  
 [EDI 文字セットのサポート](http://go.microsoft.com/fwlink/p/?LinkId=271250)