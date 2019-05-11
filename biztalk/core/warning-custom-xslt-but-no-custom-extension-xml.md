---
title: 警告 - カスタム xslt は上書きがないカスタム拡張 XML |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customXsltButNoCustomExtensionXML
ms.assetid: af008ac2-e9ae-4753-a5ba-bf4dbb711a4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4c44fbe8385717061be1e5d8e81587d6a287b7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393710"
---
# <a name="warning---custom-xslt-but-no-custom-extension-xml"></a>警告 - カスタム xslt は上書きがないカスタム拡張 XML
**エラー コード**  
  
 btm1034  
  
 **説明**  
  
 **カスタム XSLT パス**プロパティが上書きされましたが、**カスタム拡張 XML**オーバーライドされるプロパティ。 これが意図的な場合は、この警告を無視できます。  
  
 BizTalk マッパーがで指定された XSLT を使用して、**カスタム XSLT パス**プロパティと、ダミーの拡張 XML マッピング ファイルを生成します。 指定されたカスタム XSLT 内から外部アセンブリへの呼び出しを行った場合を使用してファイルを指定する必要があります、**カスタム拡張 XML**アセンブリ名マップのプレフィックスを格納するプロパティ。  
  
 **ユーザーの操作**  
  
 値を設定するかこの警告で報告された状態が意図的でない場合、**カスタム拡張 XML**上書きした値にプロパティまたは削除、**カスタム XSLT パス**プロパティ。