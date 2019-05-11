---
title: 警告 - カスタム XSLT およびカスタム拡張 XML を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.usingCustomXsltAndExtensionXML
ms.assetid: b86da5fb-6435-4e3b-89b6-d9d036b5152b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce44d40fd726731261536b622fdb9b24c65f4281
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393641"
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a>警告 - カスタム XSLT およびカスタム拡張 XML を使用します。
**エラー コード**  
  
 btm1035  
  
 **説明**  
  
 上書きのプレゼンスの値を**カスタム XSLT パス**と**カスタム拡張 XML**プロパティがすべてのマッピングを完全に無視します、このマップによって生成された出力インスタンス メッセージを制御します。元と送信先スキーマの間に指定します。 これが意図的な場合は、この警告を無視できます。  
  
 これが有効な 1 つのシナリオが BizTalk マッパーを使用して、マッピング用の一次 XSLT を生成する、特定の追加要件を満たすには、手動でこの XSLT を変更およびの値として、変更されたファイルを指定するには、**カスタム XSLT パス**プロパティ、後続のマッピング操作中に、一次 XSLT は上書きされます。  
  
 **ユーザーの操作**  
  
 このマップ内で指定されたマッピングを上書きしない場合は、上書き値を削除、**カスタム XSLT パス**プロパティおよび**カスタム拡張 XML**適切なプロパティ。