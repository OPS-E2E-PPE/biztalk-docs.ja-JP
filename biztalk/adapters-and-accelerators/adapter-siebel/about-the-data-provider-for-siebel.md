---
title: Data Provider 用 Siebel に関する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, overview
ms.assetid: 461fe4d8-75f2-49d5-9fc2-3baab4ccf13f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cac425bf1671166b4f40cecae3e1a3aca1c8e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217762"
---
# <a name="about-the-data-provider-for-siebel"></a>Data Provider 用 Siebel について
## <a name="overview"></a>概要
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]の上に構築された、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。 使用することができます、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]に。  
  
-   Siebel システムへの接続に、ADO.NET クライアントを記述します。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]プロバイダーとのインターフェイスを有効にする特定のクラスを公開します。  
  
-   Siebel ビジネス コンポーネントで SELECT クエリを実行します。
  
-   Siebel ビジネス サービスで EXEC クエリを実行します。
  
-   使用して、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と SQL Server Integration Services (SSIS)
  
[Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)が上の情報に役立つ優れたリソース。  
  
-   ADO.NET インターフェイスを拡張して、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]  
  
-   Siebel システムへの接続への接続文字列  
  
-   選択と EXEC ステートメントの構文  
  
-   使用して、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と SSIS  
  
## <a name="limitations"></a>制限事項
次はの既知の制限、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]をサポートしている別名テーブルでの名前、WHERE 句ではなく、SELECT 句でします。  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]特殊文字が含まれている列名を持つテーブルの作成に失敗"]"です。 特殊文字をエスケープするには、別の終わり角かっこを含むです。 そのため、含めるように"]"の代わりに"]"です。  
  
-   基になる Siebel クライアント API によるタイムアウトの処理に関する問題のため、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コマンドと接続のタイムアウトをサポートしていません。  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]非同期コマンドの動作をサポートしていません。  
  
-   SQL Server Integration Services (SSIS) プロジェクトで使用する場合、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 8000 以上の文字の値が含まれている列のデータの取得に失敗します。 これに基づいて、SSIS の制限のため次に示します。  
  
    -   SSIS 変数内の 4,000 文字より大きい値を指定することはできません。  
  
    -   4000 のワイド文字を超える値はサポートされていません。  
  
    -   1 バイト文字で 8000 を超える値はサポートされていません。  
  
-   EXEC 操作が使用中に機能しなくなります、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] SQL Server Integration Services (SSIS) にします。 そのため、たとえば、アダプター クライアントできなくで Siebel ビジネス サービスを実行する (を使用して[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) と SSIS のデータ プロバイダーを使用しているときにします。 

## <a name="see-also"></a>参照
[Siebel アダプターの制限事項](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)