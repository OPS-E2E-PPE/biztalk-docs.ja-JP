---
title: フラット ファイル スキーマの位置指定レコードの解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], flat file documents
- pipeline components [custom], parsing
ms.assetid: 1ceb8c06-ac21-490e-b3d5-54e5035e5f6a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e7b816e345fde33a29515333f4498d6ab744043
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395069"
---
# <a name="parsing-flat-file-schemas-with-positional-records"></a>フラット ファイル スキーマの位置指定レコードの解析
サイズの異なる位置指定レコードを持つフラット ファイル スキーマを解析するときに、各スキーマのレコードまたは各位置指定レコードのサイズを示すトレーラー内にタグを含める必要があります。 それ以外の場合、解析エンジンは最長レコード サイズを返します。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)