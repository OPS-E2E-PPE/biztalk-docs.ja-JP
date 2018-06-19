---
title: EDI スキーマの開発 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a8fbf3d-ebc7-47f6-87fa-e45722651262
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b241b5d0477d7aa477511c43b642e4e312f2651a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239282"
---
# <a name="developing-edi-schemas"></a>EDI スキーマの開発
このセクションの各トピックでは、EDI スキーマを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用できるように変更する方法について説明します。  
  
 ソリューションでドキュメント スキーマを使用するには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で BizTalk プロジェクトにスキーマを追加して展開した後、プロジェクトをビルドおよび展開する必要があります。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]既定の BizTalk アプリケーション 1 でプロジェクトを配置します。 開くことによって展開されているスキーマを表示、**スキーマ**ノードの下**BizTalk アプリケーション 1**ノード、**アプリケーション**内のノード、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 コマンド ライン展開ツール `BTSTask` を使用すると、アセンブリをさまざまなアプリケーションに展開できます。  
  
 サービスおよび管理スキーマは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードによって自動的に展開されます。 これらを参照する をクリックして、**スキーマ**内のノード、 **BizTalk EDI アプリケーション**管理コンソール内のノードです。 これらのスキーマの詳細については、次を参照してください。 [EDI サービスと管理スキーマ](../core/edi-service-and-control-schemas.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI スキーマを変更します。](../core/modifying-edi-schemas.md)  
  
-   [エンベロープ スキーマで列挙をカスタマイズします。](../core/customizing-enumerations-in-the-envelope-schema.md)  
  
-   [クロス フィールド検証の構成](../core/configuring-cross-field-validation.md)  
  
## <a name="see-also"></a>参照  
 [開発および BizTalk Server EDI ソリューションを構成します。](../core/developing-and-configuring-biztalk-server-edi-solutions.md)