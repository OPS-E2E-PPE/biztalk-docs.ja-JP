---
title: MapHelper クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c552c066-835f-4515-939f-dd465a7a5ed0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1442fbf7185a9be8cae598d1d5f2fee48f751ba2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399721"
---
# <a name="the-maphelper-class"></a>MapHelper クラス
使用して、 **MapHelper**変換 Web サービスを使用せずに直接変換を実行するクラス。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]インストーラーは、アセンブリを登録、 **Microsof.Practices.ESB.Transform.dll**で、 **MapHelper**グローバル アセンブリ キャッシュ内のクラス。  
  
 **MapHelper**クラスは、2 つのパブリック メソッドを公開します。  
  
-   **TransformMessage**します。 このメソッドは、変換するメッセージを含む文字列と BizTalk にデプロイされているマップの完全修飾名を格納する文字列パラメーターとして受け取ります。 メソッドは、変換されたドキュメントを含む文字列を返します。  
  
-   **TransformMessageStream**します。 このメソッドは、変換するメッセージを格納しているストリームと BizTalk にデプロイされているマップの完全修飾名を格納する文字列パラメーターとして受け取ります。 メソッドは、変換されたドキュメントを含む文字列を返します。