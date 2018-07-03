---
title: Data Provider for Siebel について |Microsoft Docs
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
ms.openlocfilehash: 97d7366ba227c16a5910a8000e57e92f992d3e1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989579"
---
# <a name="about-the-data-provider-for-siebel"></a>Data Provider for Siebel について
## <a name="overview"></a>概要
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]の上に構築、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。 使用することができます、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]に。  
  
- Siebel システムへの接続に、ADO.NET クライアントを記述します。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]プロバイダーとやり取りするための特定のクラスを公開します。  
  
- Siebel ビジネス コンポーネントで SELECT クエリを実行します。
  
- Siebel ビジネス サービスで EXEC クエリを実行します。
  
- 使用して、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]で SQL Server Integration Services (SSIS)
  
[.NET Framework データ プロバイダーを使用して、Siebel eBusiness Applications の](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)で有用なリソースについては。  
  
- ADO.NET インターフェイスを拡張して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]  
  
- Siebel システムへの接続への接続文字列  
  
- 選択と EXEC ステートメントの構文  
  
- 使用して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] SSIS を使用しました。  
  
## <a name="limitations"></a>制限事項
次の制限事項を呼びます、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] WHERE 句ではなく、SELECT 句で、テーブル名でサポート エイリアス。  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]特殊文字の列名でのテーブルの作成に失敗"]"。 もう 1 つの角かっこを含めることによって、特殊文字をエスケープできます。 そのため、含める必要がある"]"の代わりに"]"。  
  
- 基になる Siebel クライアント API によってタイムアウト処理に関する問題のため、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コマンドと接続のタイムアウトをサポートしていません。  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]非同期コマンドの動作をサポートしていません。  
  
- SQL Server Integration Services (SSIS) プロジェクトで使用する場合、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 8000 以上の文字の値を含む列のデータの取得に失敗します。 これに基づいて、SSIS の制限が原因です。  
  
  -   SSIS 変数に 4,000 文字よりも大きい値がサポートされていません。  
  
  -   4000 のワイド文字を超える値はサポートされていません。  
  
  -   1 バイト文字で 8000 を超える値はサポートされていません。  
  
- EXEC 操作が使用中に機能しなくなります、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] SQL Server Integration Services (SSIS) とします。 そのため、たとえば、アダプター クライアントできなくで Siebel ビジネス サービスを実行する (を使用して[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) SSIS を使用したデータ プロバイダーを使用しているときにします。 

## <a name="see-also"></a>参照
[Siebel アダプターの制限事項](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[Siebel アダプターをトラブルシューティングします。](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)