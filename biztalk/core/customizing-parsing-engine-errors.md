---
title: 解析エンジン エラーのカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], errors
- pipeline components [custom], code samples
ms.assetid: d9a0060b-49c0-4690-956b-d31668f23c41
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16fc2fbaa8d8dea2f298a54eb6a090ab1f43a733
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390046"
---
# <a name="customizing-parsing-engine-errors"></a>解析エンジン エラーのカスタマイズ
エラーを処理する解析エンジンを使用して、独自のエラー処理のコールバックを登録できます。  
  
## <a name="example"></a>例  
  
```  
bool MyErrorHandler(ErrorContext ctx)  
{  
   // Handle the error  
   return true;  
   // true=continue parsing, false=stop  
}  
  
FFReader ffr = (FFReader)docspec.Parse(new DataReader());  
ffr.OnErrorEvent += MyErrorHandler;  
```  
  
## <a name="see-also"></a>参照  
 [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)