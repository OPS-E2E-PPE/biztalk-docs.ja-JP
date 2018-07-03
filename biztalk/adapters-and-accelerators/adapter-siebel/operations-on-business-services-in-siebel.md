---
title: Siebel ビジネス サービスに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24fa8ee0bd51ddf919e5f88a47ceae9d0743fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001371"
---
# <a name="operations-on-business-services-in-siebel"></a>Siebel ビジネス サービスに対する操作
Siebel ビジネス サービスは、Siebel に直接呼び出すことができるビジネス メソッドのコレクションです。 一方、ビジネス コンポーネントとビジネス オブジェクトが特定のデータ、および Siebel のテーブルに関連付けられていると、ビジネス サービスは、特定のタスクを実行するオブジェクトを呼び出します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]操作名し、サポート、IN、OUT および INOUT パラメーターとビジネス サービス メソッドは、明らかになります。 たとえば、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェス、 **ATPRunCheck**操作としてメソッド。 このメソッドが属する、 **ATP**ビジネス サービス。  
  
 特定の条件、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel ビジネス サービスを使用しているときに。  
  
- Siebel ビジネス サービス メソッドが指定されたデータ型がない引数を受け取る場合、アダプターは、テキストとして、引数を公開します。  
  
- Siebel ビジネス サービス メソッドの引数は、次の種類のできます。  
  
  - 文字列 (xsd:string として公開)  
  
  - 数 (xsd として公開します 10 進数)。  
  
  - 日付 (時刻部分が 00時 00分: 00 に設定する必要がありますでパターン ファセットを示すの xsd:DateTime として公開)  
  
  - 階層 (xsd:string として公開)  
  
  - (Xsd:string として公開) の統合オブジェクト  
  
    また、ビジネス サービス メソッドでは、引数に渡された値が、対応する型に準拠しているかどうかを確認します。 したがって、ビジネス サービス メソッドを受け入れるか、対応する引数の型に準拠していない値を返す場合、アダプターが例外をスローします。 ビジネス サービス メソッドを呼び出す際に、アダプターが成功した場合、スキーマの検証が失敗します。  
  
  詳細については。  
  
- BizTalk Server を使用してビジネス サービスに対する操作を実行するを参照してください[呼び出すビジネス サービス メソッドを使用して BizTalk Server と Siebel アダプター](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)します。  
  
- メッセージの構造と SOAP アクションのビジネス サービスに対する操作の実行を参照してください[ビジネス サービス操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md))。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)