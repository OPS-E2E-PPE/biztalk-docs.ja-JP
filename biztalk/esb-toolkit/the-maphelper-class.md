---
title: MapHelper クラス |Microsoft ドキュメント
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
ms.openlocfilehash: de74610c40b37560abcbce040d80320525f0a21c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295114"
---
# <a name="the-maphelper-class"></a>MapHelper クラス
使用して、 **MapHelper**変換 Web サービスを使用せずに直接変換を実行するクラス。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]インストーラーは、アセンブリを登録、 **Microsof.Practices.ESB.Transform.dll**で、 **MapHelper**グローバル アセンブリ キャッシュ内のクラスです。  
  
 **MapHelper**クラスは、次の 2 つのパブリック メソッドを公開します。  
  
-   **TransformMessage**です。 このメソッドは、変換するメッセージを含む文字列と BizTalk に展開されているマップの完全修飾名を含む文字列パラメーターとして受け取ります。 メソッドは、変換されたドキュメントを含む文字列を返します。  
  
-   **TransformMessageStream**です。 このメソッドは、変換するメッセージを格納しているストリームと BizTalk に展開されているマップの完全修飾名を含む文字列パラメーターとして受け取ります。 メソッドは、変換されたドキュメントを含む文字列を返します。