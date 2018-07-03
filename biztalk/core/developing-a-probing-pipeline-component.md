---
title: パイプライン コンポーネントの開発、プローブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], probing
- IProbeMessage interface
- pipeline interfaces, IProbeMessage
ms.assetid: c3da467d-5270-4c7f-9c38-ce9989bf1b63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be44929609eaba5ec30a6e40c1bdda14192e351
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987363"
---
# <a name="developing-a-probing-pipeline-component"></a>プローブ パイプライン コンポーネントの開発
任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できる、`IProbeMessage`インターフェイスの場合はメッセージ プローブ機能をサポートする必要があります。 プローブ コンポーネントがされているパイプライン ステージで使用される**FirstMatch**実行モード。 このモードのステージでは、BizTalk Server メッセージング エンジンからプローブ コンポーネントにメッセージの先頭部分が渡され、コンポーネントで認識できる形式のメッセージかどうかが確認されます。 コンポーネントで認識できる形式の場合は、メッセージ全体が対応するコンポーネントに渡され、処理されます。  
  
 **IProbeMessage**インターフェイスは 1 つのメソッドを公開**プローブ**、使用して、コンポーネントをメッセージの先頭部分を確認します。 戻り値により、このコンポーネントが実行されているかどうかが決まります。 以下の手順に、BizTalk メッセージング エンジンで、認識が必要なステージを実行する方法を示します。  
  
1. ステージにコンポーネントが含まれていない場合、ステージは実行されず、メッセージが後続のステージに渡されて処理されます。  
  
2. コンポーネントを実装するかどうかの確認、 **IProbeMessage**インターフェイス。 実装されていない場合、メッセージング エンジンはコンポーネントを呼び出します。 ステージ処理が実行され、メッセージが次のステージに渡されます。  
  
3. **プローブ**メソッドが呼び出されます。 戻り値が場合**True**コンポーネントを実行します。 この場合、ステージ処理が実行され、メッセージが次のステージに渡されます。  
  
4. メッセージング エンジンは、ステージの次のコンポーネントを取得します。 追加のコンポーネントが存在せず、どのコンポーネントも実行されていない場合、パイプライン処理が失敗したことを示すエラーが生成されます。 追加のコンポーネントが存在せず、1 つ以上のコンポーネントが実行されている場合、処理が実行されます。  
  
   ステージに認識が必要としない場合 (たとえば、実行モードは**すべて**)、メッセージング エンジンは、最初のクエリを実行することがなく、コンポーネントを呼び出します、 **IProbeMessage**インターフェイスと呼び出し、**プローブ**メソッド。  
  
## <a name="see-also"></a>参照  
 [全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md)   
 [アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md)   
 [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)   
 [パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)