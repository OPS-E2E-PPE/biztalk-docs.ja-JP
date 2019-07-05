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
ms.openlocfilehash: b6fb92d0b8a20e9ca4e1a71aead55af21b1daeea
ms.sourcegitcommit: bab8f4abca27edc45f9f4601ada6f3fc6a2b87cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/04/2019
ms.locfileid: "65394782"
---
# <a name="x12-edi-character-set"></a>X12 EDI 文字セット
&#Xd1; という文字またはアクサン グラーブ (') を使用する場合は、次のことを指定します。  


|                                                                   |                                  文字セット                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             EDI ドキュメント内の &#xd1; という文字のみ              |                            拡張文字セットを使用します。                            |
|           のみの抑音アクセント (\`) で、EDI ドキュメント            |                              UTF8 文字セットを使用します。                              |
| &#Xd1; という文字**と**アクサン グラーブ (\`)、同じドキュメント内。 | -UTF8 エンコード受信ドキュメントである必要があります。<br />-UTF8 文字セットを使用します。 |

 次のリンク プロバイダー EDI 文字セットの詳細について。  

 [EDI 文字セット](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [EDI 文字セットのサポート](http://go.microsoft.com/fwlink/p/?LinkId=271250)