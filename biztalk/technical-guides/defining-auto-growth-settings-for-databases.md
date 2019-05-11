---
title: データベースの自動拡張設定の定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd86dd49-6505-4673-b413-d3af729dfca9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c2070ae827136a5b03cb51ef0697db0180fe5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305946"
---
# <a name="define-auto-growth-settings-for-databases"></a>データベースの自動拡張設定を定義します。
データベース自動拡張は、固定の代わりに、メッセージ ボックス データベースおよび BizTalk 追跡データベースの特にのパーセント値のメガバイト数に設定する必要があります。 BizTalk アプリケーションとスループットに応じて、メッセージ ボックス データベースと追跡データベースを非常に大きく取得できます。 自動拡張をパーセンテージに設定した場合、自動拡張相当する場合がもします。  
  
## <a name="how-instant-file-initialization-works"></a>どのインスタント ファイルの初期化のしくみ  
 SQL Server には、ファイルのサイズが大きくとき、は、新しいスペースまず初期化を可能にする前に、必要があります。 これは、空のページで、新しい領域の入力を含むブロッキング操作です。 Windows 上の SQL Server は、「ファイルの瞬時初期化します。」をサポートしています。 これは、ファイルの拡張操作のパフォーマンスに与える影響を大幅に削減できます。 詳細については、「 [データベース ファイルの初期化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)」を参照してください。 このトピックでは、ファイルの瞬時初期化を有効にするに必要な手順について説明します。  
  
## <a name="enable-instant-file-initialization"></a>ファイルの瞬時初期化を有効にします。  
 即時有効にする手順は、初期化ファイルを参照してください[データベース ファイルの初期化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)します。 ファイル グループを作成すると、適切なファイル グループに BizTalk Server データベース テーブル、インデックス、およびログ ファイルを移動する、推奨事項に従い、 [BizTalk パフォーマンス最適化ガイド](../technical-guides/biztalk-server-2013-performance-optimization-guide.md)します。 理想的にはファイル グループをサポートしているファイルのサイズを事前に割り当てられるし、可能であれば、静的なサイズに設定する必要があります。  
  
 ファイルを構成し、システムが新しい静的サイズが決定的確立されていない場合、**自動拡張を有効にする**オプションし、ファイルの拡張を指定**メガバイト単位で**します。 拡張増分値は、100 MB (サイズの大きいファイル) を (中規模ファイル用)、10 MB または 1 MB (小さなファイル) の以下通常場合があります。
