---
title: "BizTalk Server2 における EDI のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6162276e5e394bd17b75825535ddaf097a7f589c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-support-in-biztalk-server"></a>BizTalk Server における EDI のサポート
バージョンの異なる [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、次に示すさまざまな機能およびコンポーネントを通じて EDI をサポートしています。  
  
|リリース|EDI サポートを提供するコンポーネントおよび機能|  
|---|---|  
|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]、以降のすべてのバージョン|ネイティブの EDI 機能|  
|[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]|ベース EDI アダプタ|  
|[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]|ベース EDI アダプタ|  
|[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]|ネイティブの EDI 機能|  
  
## <a name="feature-set-comparison-chart"></a>機能セットの比較表  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] リリースの EDI コンポーネントおよび機能によって提供される EDI サポートを次の表に示します。 「Y」はサポートされる機能、「N」はサポートされない機能を表します。  
  
|機能|[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] - [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]|[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] - [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]|BizTalk Server 2009|BizTalk Server 2010|解説|  
|---|---|---|---|---|---|---|  
|トランザクション セットでの ISA セグメントの変更|Y|×|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 以降では、トランザクション セット固有のアグリーメントを作成することによってサポートされています。|  
|ISA11: 米国またはその他の標準の型|Y|×|Y|Y|Y|-|  
|[Isa12]: インターチェンジ制御バージョン|Y|×|Y|Y|Y|-|  
|Isa 13: インターチェンジ制御番号 (番号の増分)|Y|×|Y|Y|Y|-|  
|Isa 15: テストまたは実稼働|Y|×|Y|Y|Y|-|  
|ドキュメント/トランザクション レベルでの GS セグメントの変更|Y|×|Y|Y|Y|-|  
|ISA と異なる GS 送信者/受信者 Id の許可|Y|×|Y|Y|Y|-|  
|ISA および GS の送信 Id と異なる受信ドキュメント Id|Y|×|Y|Y|Y|-|  
|ドキュメントの種類を変更する GS01: 機能|Y|×|Y|Y|Y|-|  
|GS04: 日付 (形式を変更する機能)|×|×|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 以降には、CCYYMMDD および YYMMDD の形式を選択する UI があります。|  
|GS05: 時間 (書式を変更する機能)|×|×|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 以降には、HHMM、HHMMSS、HHMMSSdd の形式を選択する UI があります。|  
|GS06: 制御番号を変更します。|Y|×|Y|Y|Y|-|  
|GS07: 機関コード|Y|×|Y|Y|Y|-|  
|GS08: 標準バージョンを配置すること|Y|×|Y|Y|Y|-|  
|実行時に EDI エンベロープを上書きする機能|×|×|×|Y|Y|-|  
|カスタム EDI スキーマ|Y|×|Y|Y|Y|-|  
|組織/パーティの設定|Y|○ (最小限)|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] と BizTalk Server 2009 では、テンプレートに基づいてパーティを作成できます。<br /><br /> BizTalk Server 2010 以降では、パーティとアグリーメントを分離することによって、これをモデル化し直しています。 テンプレートに基づいてアグリーメントを作成できます。|  
|EDI ドキュメントのドキュメント定義を介したルーティング|Y|-|Y|Y|Y|-|  
|取引先への自動 997|Y|Y|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] と BizTalk Server 2009 では、パーティ固有の構成でサポートされます。<br /><br /> BizTalk Server 2010 以降では、ビジネス プロファイル固有の構成でサポートされます。|  
|信頼性の高いメッセージング 997 経由で送信 EDI|Y|Y|Y|Y|Y|-|  
|EDIFACT のサポート|Y|○ (最小限)|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 以降でサポートされます (ISO 9735 v4.1 につき D93～D05 )。|  
|X12 サポートします。|Y|○ (最小限)|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 以降でサポートされます (2040～5030)。|  
|HIPAA サポート|×|○ ([!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 内)|Y|Y|Y|サポートされる[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) 3.3 として。 [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 以降では、ネイティブ EDI 機能の一部としてサポートされています。|  
|列挙子/コードリストの削除機能|Y|×|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 以降では、Visual Studio/BizTalk Editor でサポートされています。|  
|AS2 の送信/受信|×|×|Y|Y|Y|BizTalk Server 2009 以降では、AS2 は複数ファイルの添付ファイルのサポート、ファイル名保持のサポートと相互運用性です。|  
|AS2 ファイル名の保持|×|×|×|Y|Y|-|  
|AS2 の信頼できるメッセージング|×|×|×|Y|Y|-|  
|移行できる[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]EDI リポジトリへのカスタム XDR EDI スキーマ|-|×|×|×|×|Base EDI アプリを [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] または BizTalk Server 2009 に移行する必要があります。次に、パーティ移行ツールを使用してアプリを BizTalk Server 2010 以降に移行します。|  
|送信バッチ処理が (複数の種類のトランザクションを 1 つのトランザクションにまとめる)|×|×|Y|Y|Y|BizTalk Server 2009 以降では、各ビジネス プロファイルについて複数のバッチ構成をサポートしています。|  
|受信バッチ処理、– インターチェンジ XML ("バッチ化された"受信インターチェンジを保存) またはトランザクション セット XML 構成オプション|×|×|Y|Y|Y|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] 以降では、受信のバッチ解除、つまり、インターチェンジを分離して個別のトランザクション セット Xml にする処理もサポートされます。|  
|インターチェンジおよびトランザクション セットの生成と検証 Visual Studio でのデザイン時|×|×|Y|Y|Y|-|  
|TA1 (技術確認) の生成と調整|×|×|Y|Y|Y|-|  
|省略可能な EDI および XSD 検証フラグ|×|×|Y|Y|Y|-|  
|GS レベルでドキュメントの形式と定義|×|×|Y|Y|Y|-|  
  
## <a name="see-also"></a>参照  
 [EDI 標準のサポート](../core/edi-standards-support.md)   
 [EDI ドキュメント スキーマのサポート](../core/edi-document-schema-support.md)   
 [EDI 文字セットのサポート](../core/edi-character-set-support.md)