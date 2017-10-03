---
title: "データベースの自動拡張設定を定義する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd86dd49-6505-4673-b413-d3af729dfca9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d702898cdaab8f9993fdc9b901e34f51ba6941c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defining-auto-growth-settings-for-databases"></a>データベースの自動拡張設定を定義します。
データベースの自動拡張は、の代わりに、メッセージ ボックス データベースと BizTalk 追跡データベースの特にのパーセント値のメガバイト数が固定に設定する必要があります。 BizTalk アプリケーションとスループット、に応じて、メッセージ ボックス データベースおよび追跡データベースを非常に大きい取得できます。 パーセンテージを自動拡張を設定した場合、自動拡張できますかなり大きくなる場合もします。  
  
## <a name="how-instant-file-initialization-works"></a>どの瞬時ファイル初期化 Works  
 SQL Server では、ファイルのサイズを大きく、ときに、新しい領域最初初期化を使用する前に、必要があります。 これは、ブロッキング操作を含む空のページで、新しい領域の情報を入力します。 [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]「ファイルの瞬時初期化」をサポートしている Windows Server 2003 以降を実行して、後で、または これは、ファイルの拡張操作のパフォーマンスに与える影響を大幅に減らすことができます。 詳細については、次を参照してください。 ["データベース ファイルの初期化"](http://go.microsoft.com/fwlink/?LinkId=101579) (http://go.microsoft.com/fwlink/?LinkId=101579) SQL Server のドキュメントにします。 このトピックでは、ファイルの瞬時初期化を有効にする際に必要な手順について説明します。  
  
## <a name="enabling-instant-file-initialization"></a>ファイルの瞬時初期化を有効にします。  
 インスタント有効にする方法の手順は、初期化ファイルを参照してください[「データベース ファイルの初期化」](http://go.microsoft.com/fwlink/?LinkId=101579) (http://go.microsoft.com/fwlink/?LinkId=101579) SQL Server のドキュメントにします。 ファイル グループを作成すると、移動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース テーブル、インデックス、および適切なファイル グループにログ ファイルで「付録 B-推奨される BizTalk Server データベース構成」推奨事項に従い、 ["BizTalkサーバーのデータベースの最適化」ホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578)。 理想的にはファイル グループをサポートするファイルのサイズを事前に割り当てられるし、可能な場合は、静的なサイズに設定する必要があります。  
  
 ファイルを構成し、システムが新しい静的なサイズが決定的確立されていない場合は、**自動拡張を有効にする**オプションし、ファイル拡張を指定**メガバイト単位で**です。 拡張増分値を超える 100 MB (サイズの大きいファイル)、10 MB (中規模ファイル用)、または 1 MB (小さなファイル用)、通常場合があります。