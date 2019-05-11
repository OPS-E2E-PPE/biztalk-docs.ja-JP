---
title: 警告 - カスタム拡張 XML がないカスタム xslt は上書き |Microsoft Docs
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
ms.openlocfilehash: 0d94bea29ee6943ee6b084518e4b4ff404377503
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393727"
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a>警告 - カスタム拡張 XML がないカスタム xslt は上書き
**エラー コード**  
  
 btm1033  
  
 **説明**  
  
 **カスタム拡張 XML**プロパティが上書きされましたが、**カスタム XSLT パス**オーバーライドされるプロパティ。 これが意図的な場合は、この警告を無視できます。  
  
 BizTalk マッパーは、マップのコンパイルによって生成された XSLT を使用してとはも拡張 XML を生成し、オーバーライドされたプロパティで指定されたカスタム拡張 XML に追加します。 これは、便利な場合、マップが含まれています**Scripting**インライン XSLT またはインライン XSLT を使用して、functoid が外部アセンブリ内の 1 つまたは複数のメソッドの呼び出しを構成するテンプレートを呼び出します。 このような場合、ユーザーでアセンブリ名マップにプレフィックスを指定、**カスタム拡張 XML**プロパティ。  
  
 **ユーザーの操作**  
  
 値を設定するかこの警告で報告された状態が意図的でない場合、**カスタム XSLT パス**上書きした値にプロパティまたは削除、**カスタム拡張 XML**プロパティ。