---
title: X12 EDI 文字セット |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bd501c81b92f4fa7824009a949fd6c7e58eaf3b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023104"
---
# <a name="x12-edi-character-set"></a>X12 EDI 文字セット
& #Xd1; という文字またはアクサン グラーブ (') を使用する場合は、次のことを指定します。  


|                                                                   |                                  文字セット                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             EDI ドキュメント内の & #xd1; という文字のみ              |                            拡張文字セットを使用します                            |
|           のみの抑音アクセント (\`) で、EDI ドキュメント            |                              UTF8 文字セットの使用                              |
| & #Xd1; という文字**と**アクサン グラーブ (\`)、同じドキュメント内。 | -UTF8 エンコード受信ドキュメントである必要があります。<br />-UTF8 文字セットを使用します。 |

 EDI 文字セットの詳細については、次のリンクを参照してください。  

 [EDI 文字セット](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [EDI 文字セットのサポート](http://go.microsoft.com/fwlink/p/?LinkId=271250)