---
title: 警告 - カスタム拡張 XML がないカスタム xslt は上書き |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customExtensionXmlButNoCustomXSLT
ms.assetid: 3219c73c-2e58-4fe2-bc6e-2d60348d2415
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b626f8ede3231c04ae74dc0097cbdf524c90522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288226"
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a>警告 - カスタム拡張 XML がないカスタム xslt は上書き
**エラー コード**  
  
 btm1033  
  
 **説明**  
  
 **カスタム拡張 XML**プロパティが上書きされましたが、**カスタム XSLT パス**オーバーライドされるプロパティです。 これを意図的に行っている場合は、この警告を無視してください。  
  
 BizTalk マッパーは、マップをコンパイルして作成された XSLT を使用します。また、拡張 XML を生成して、上書き先のプロパティで指定されているカスタム拡張 XML に追加します。 これを利用する、マップが含まれている**スクリプト**インライン XSLT またはインライン XSLT を使用する functoid を呼び出す外部アセンブリの 1 つまたは複数のメソッドの呼び出しを構成するテンプレートです。 このような場合、ユーザーでアセンブリ名マップにプレフィックスを指定、**カスタム拡張 XML**プロパティです。  
  
 **ユーザーの操作**  
  
 互換性のある値を設定するか場合、この警告で報告された状態が意図しないもので、**カスタム XSLT パス**上書きした値をプロパティ、または削除、**カスタム拡張 XML**プロパティです。