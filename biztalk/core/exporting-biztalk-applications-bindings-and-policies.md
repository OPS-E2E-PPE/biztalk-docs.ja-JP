---
title: BizTalk アプリケーション、バインド、およびポリシーのエクスポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- exporting, policies
- bindings, exporting
- exporting, applications
- applications, exporting
- exporting, bindings
ms.assetid: ac101206-be49-47c9-a354-4f39e8b77acf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6df445b0fefc132940a736870d66c62329ce60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245810"
---
# <a name="exporting-biztalk-applications-bindings-and-policies"></a>BizTalk アプリケーション、バインド、およびポリシーのエクスポート
ここでは、BizTalk アプリケーション、バインド、またはポリシーをエクスポートする方法について説明します。 BizTalk アプリケーションに含まれるアイテムの一部またはすべてをエクスポートすることも、バインドまたはポリシーだけをエクスポートすることもできます。 アプリケーションをエクスポートすると、Windows インストーラー (.msi) ファイルが作成されます。このファイルには、エクスポートするよう選択したアプリケーションのアイテムが含まれます。 バインドまたはポリシーをエクスポートすると、バインドまたはポリシーの .xml ファイルが作成されます。 このプロセスの基礎知識については、次を参照してください。[発生時に成果物はエクスポート内容](../core/what-happens-when-artifacts-are-exported.md)です。  
  
 アプリケーションの .msi ファイルを別の BizTalk グループにインポートして、アプリケーションのアイテムをそのグループ内に含む新しいアプリケーションを作成できます。 バインドまたはポリシーの .xml ファイルを別の BizTalk アプリケーションにインポートすると、そのバインドまたはポリシーを使用できます。 アイテムをインポートする方法については、「[をインポートする BizTalk アプリケーション バインド、およびポリシー](../core/importing-biztalk-applications-bindings-and-policies.md)です。  
  
> [!IMPORTANT]
>  バインド ファイルには接続情報や構成情報などの重要なビジネス データが含まれる可能性があるため、安全な場所に保存してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)  
  
-   [バインドをエクスポートします。](../core/exporting-bindings6.md)  
  
-   [ポリシーをエクスポートする方法](../core/how-to-export-a-policy.md)