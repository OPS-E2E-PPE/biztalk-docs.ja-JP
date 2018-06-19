---
title: XML ツール拡張機能の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5613bf15-6c0a-4a82-b200-24d0801d7ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 976082fc14eb37d550956ec447eb63938706daa3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006315"
---
# <a name="using-the-xml-tool-extensions"></a>XML ツール拡張の使用
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の XML ツール拡張を使用すると、スキーマ、マップ、およびメッセージ インスタンスに対してタスクを実行できます。 これらの拡張は、デザイン時に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境で使用します。 実行できるタスクは次のとおりです。  
  
-   **スキーマの検証**です。 この操作では、EDI ルールに基づいて、EDI スキーマを検証します。 詳細については、次を参照してください。[スキーマ (EDI) を検証する](../core/validating-a-schema-edi.md)です。  
  
-   **メッセージ インスタンスの検証**です。 この操作では、単一のトランザクション セット (インターチェンジ ヘッダーとグループ ヘッダーを含まない)、または複数のトランザクション セットを含む完全なバッチ化されたインターチェンジ (インターチェンジ ヘッダーとグループ ヘッダーを含む) を検証します。 バッチ化されていないインターチェンジを検証するには、インターチェンジ ヘッダーとグループ ヘッダーをインスタンスから削除する必要があります。 詳細については、次を参照してください。 [(EDI) インスタンスを検証する](../core/validating-an-instance-edi.md)です。  
  
-   **メッセージ インスタンスを生成する**です。 この操作では、完全なバッチ化されたインターチェンジ、またはインターチェンジ ヘッダーとグループ ヘッダーを含まないトランザクション セットを生成します。 インスタンスの生成に使用する区切り記号や識別子などの形式を指定する必要があります。 詳細については、次を参照してください。[インスタンス (EDI) を生成する](../core/generating-an-instance-edi.md)です。  
  
-   **マップのテスト**です。 この操作では、処理対象ドキュメントとマップに基づき、架空のデータを使用した出力ドキュメントを生成します。 詳細については、次を参照してください。[マップのテスト](../core/testing-a-map.md)です。  
  
-   **マップの検証**です。 検証を行うと、マップの基になる XSLT を含むファイルと、拡張オブジェクトを含むファイルが生成されます。 詳細については、次を参照してください。[マップ (EDI) を検証する](../core/validating-a-map-edi.md)です。  
  
 BizTalk Server で、これらの拡張機能は、EDI スキーマ、マップ、およびメッセージ インスタンスで動作します。 これらの拡張により、複雑な EDI のスキーマ、マップ、およびインターチェンジを、より効果的に処理できます。  
  
 XML ツール拡張は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセットアップ プログラムにより既定で有効化されます。 ソリューション エクスプ ローラーの Visual Studio で、スキーマをダブルクリックする場合、**スキーマ エディター拡張機能**スキーマのプロパティに設定されて**EDI スキーマ エディタ拡張機能**します。 この設定は、XML ツール拡張を機能させるために必要です。 EDI 拡張機能を選択したままで、他のスキーマ エディター拡張機能を選択することもできます。  
  
## <a name="see-also"></a>参照  
 [インスタンス (EDI) の生成](../core/generating-an-instance-edi.md)   
 [インスタンス (EDI) の検証](../core/validating-an-instance-edi.md)   
 [スキーマ (EDI) の検証](../core/validating-a-schema-edi.md)   
 [マップのテスト](../core/testing-a-map.md)   
 [マップの検証 (EDI)](../core/validating-a-map-edi.md)