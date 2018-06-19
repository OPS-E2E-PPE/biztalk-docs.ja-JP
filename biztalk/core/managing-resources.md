---
title: リソースの管理 |Microsoft ドキュメント
description: Btstask または BizTalk 管理コンソールを使用して、BizTalk Server で複数のアセンブリ、スクリプト、証明書、バインド ファイルで動作するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b478ef2e-1363-4c2c-a4b7-6a582a6b33a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07248c1689adf6b6474fd8e1f3e01f2d660becdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262442"
---
# <a name="manage-resources"></a>リソースを管理します。

## <a name="overview"></a>概要
ここでは、BizTalk グループに BizTalk Server リソースを展開した後、BizTalk Server 管理コンソールまたは BTSTask コマンドライン ツールを使用して BizTalk Server リソースを管理する方法について説明します。 リソースには、次の種類のアイテムが含まれます。  
  
-   BizTalk アセンブリ  
  
-   処理前および処理後のスクリプト  
  
-   .NET アセンブリ  
  
-   COM コンポーネント  
  
-   証明書  
  
-   アドホック ファイル  
  
-   BAM 定義  
  
-   バインド ファイル  
  
-   仮想ディレクトリ  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
> [!NOTE]
>  どのような場合においても、同じ名前の複数のリソースを BizTalk Server グループに追加しないでください。 BizTalk Server 管理データベースの格納先 SQL Server の構成で、バイナリ照合順序が使用され、大文字と小文字の区別がサポートされている場合でも、同じ名前の複数のリソースを BizTalk Server グループに追加することはできません。  
  
## <a name="next-steps"></a>次の手順
  
-   [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)  
  
-   [前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md)  
  
-   [.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md)  
  
-   [リソースを更新します。](../core/how-to-refresh-a-resource.md)