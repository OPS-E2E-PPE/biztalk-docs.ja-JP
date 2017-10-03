---
title: "警告 - カスタム xslt は上書きがないカスタム拡張 XML |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.warning.customXsltButNoCustomExtensionXML
ms.assetid: af008ac2-e9ae-4753-a5ba-bf4dbb711a4e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b67591e0e0dbb6b3ecac9aee1566c3245c9969a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="warning---custom-xslt-but-no-custom-extension-xml"></a>警告 - カスタム xslt は上書きがないカスタム拡張 XML
**エラー コード**  
  
 btm1034  
  
 **説明**  
  
 **カスタム XSLT パス**プロパティが上書きされましたが、**カスタム拡張 XML**オーバーライドされるプロパティです。 これを意図的に行っている場合は、この警告を無視してください。  
  
 BizTalk マッパーがで指定された XSLT を使用して、**カスタム XSLT パス**プロパティ ダミー拡張 XML マッピング ファイルを生成します。 指定されたカスタム XSLT 内から外部アセンブリへの呼び出しを行う場合を使用してファイルを指定する必要があります、**カスタム拡張 XML**とアセンブリ名のマッピング プレフィックスが含まれているプロパティ。  
  
 **ユーザーの操作**  
  
 互換性のある値を設定するか場合、この警告で報告された状態が意図しないもので、**カスタム拡張 XML**上書きした値をプロパティ、または削除、**カスタム XSLT パス**プロパティです。