# Bulk-RNA-seq
{
    "a_galaxy_workflow": "true",
    "annotation": "",
    "format-version": "0.1",
    "name": "RNA Seq",
    "steps": {
        "0": {
            "annotation": "fastq.gz",
            "content_id": null,
            "errors": null,
            "id": 0,
            "input_connections": {},
            "inputs": [
                {
                    "description": "fastq.gz",
                    "name": "Pair2"
                }
            ],
            "label": "Pair2",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "bottom": 148.95000457763672,
                "height": 49.44999694824219,
                "left": 163.0000114440918,
                "right": 323.0000114440918,
                "top": 99.50000762939453,
                "width": 160,
                "x": 163.0000114440918,
                "y": 99.50000762939453
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false, \"tag\": null}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "01d3db8a-b066-4867-bc8c-c9f05dddc6e1",
            "when": null,
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "output",
                    "uuid": "158c22c9-d894-4cfb-b2f5-76867484d8b2"
                }
            ]
        },
        "1": {
            "annotation": "fastq.gz",
            "content_id": null,
            "errors": null,
            "id": 1,
            "input_connections": {},
            "inputs": [
                {
                    "description": "fastq.gz",
                    "name": "Pair1"
                }
            ],
            "label": "Pair1",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "bottom": 247.95000839233398,
                "height": 49.45000457763672,
                "left": 163.0000114440918,
                "right": 323.0000114440918,
                "top": 198.50000381469727,
                "width": 160,
                "x": 163.0000114440918,
                "y": 198.50000381469727
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false, \"tag\": null}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "0a87770a-9dd1-4813-b9b2-212e2892474e",
            "when": null,
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "output",
                    "uuid": "dcc102f7-076c-409f-8c53-9c4ff2d21bd6"
                }
            ]
        },
        "2": {
            "annotation": "gtf",
            "content_id": null,
            "errors": null,
            "id": 2,
            "input_connections": {},
            "inputs": [
                {
                    "description": "gtf",
                    "name": "gtf_file"
                }
            ],
            "label": "gtf_file",
            "name": "Input dataset",
            "outputs": [],
            "position": {
                "bottom": 377.9500160217285,
                "height": 49.44999313354492,
                "left": 441.0000228881836,
                "right": 601.0000228881836,
                "top": 328.5000228881836,
                "width": 160,
                "x": 441.0000228881836,
                "y": 328.5000228881836
            },
            "tool_id": null,
            "tool_state": "{\"optional\": false, \"tag\": null}",
            "tool_version": null,
            "type": "data_input",
            "uuid": "ef3888f0-3fad-4559-b9ef-f1a5796ff6a9",
            "when": null,
            "workflow_outputs": [
                {
                    "label": null,
                    "output_name": "output",
                    "uuid": "28c72836-d3bb-45f6-ac74-7e8f224cb0e4"
                }
            ]
        },
        "3": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/bgruening/trim_galore/trim_galore/0.6.7+galaxy0",
            "errors": null,
            "id": 3,
            "input_connections": {
                "singlePaired|input_mate1": {
                    "id": 1,
                    "output_name": "output"
                },
                "singlePaired|input_mate2": {
                    "id": 0,
                    "output_name": "output"
                }
            },
            "inputs": [
                {
                    "description": "runtime parameter for tool Trim Galore!",
                    "name": "singlePaired"
                },
                {
                    "description": "runtime parameter for tool Trim Galore!",
                    "name": "singlePaired"
                }
            ],
            "label": null,
            "name": "Trim Galore!",
            "outputs": [
                {
                    "name": "trimmed_reads_pair1",
                    "type": "input"
                },
                {
                    "name": "trimmed_reads_pair2",
                    "type": "input"
                }
            ],
            "position": {
                "bottom": 244.02501106262207,
                "height": 188.52500915527344,
                "left": 441.0000228881836,
                "right": 601.0000228881836,
                "top": 55.50000190734863,
                "width": 160,
                "x": 441.0000228881836,
                "y": 55.50000190734863
            },
            "post_job_actions": {
                "HideDatasetActiontrimmed_reads_pair1": {
                    "action_arguments": {},
                    "action_type": "HideDatasetAction",
                    "output_name": "trimmed_reads_pair1"
                },
                "HideDatasetActiontrimmed_reads_pair2": {
                    "action_arguments": {},
                    "action_type": "HideDatasetAction",
                    "output_name": "trimmed_reads_pair2"
                }
            },
            "tool_id": "toolshed.g2.bx.psu.edu/repos/bgruening/trim_galore/trim_galore/0.6.7+galaxy0",
            "tool_shed_repository": {
                "changeset_revision": "cd7e644cae1d",
                "name": "trim_galore",
                "owner": "bgruening",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"params\": {\"settingsType\": \"custom\", \"__current_case__\": 1, \"quality\": \"20\", \"stringency\": \"1\", \"error_rate\": \"0.1\", \"min_length\": \"20\", \"clip_R1\": null, \"clip_R2\": null, \"report\": false, \"retain_unpaired\": {\"retain_unpaired_select\": \"no_output\", \"__current_case__\": 0}}, \"rrbs\": {\"settingsType\": \"default\", \"__current_case__\": 0}, \"singlePaired\": {\"sPaired\": \"paired\", \"__current_case__\": 1, \"input_mate1\": {\"__class__\": \"RuntimeValue\"}, \"input_mate2\": {\"__class__\": \"RuntimeValue\"}, \"trimming\": {\"trimming_select\": \"\", \"__current_case__\": 0}, \"trim1\": false, \"three_prime_clip_R1\": null, \"three_prime_clip_R2\": null}, \"trimming\": {\"settingsType\": \"default\", \"__current_case__\": 0}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.6.7+galaxy0",
            "type": "tool",
            "uuid": "7bb85dba-e182-4a1a-b38a-149a8703782c",
            "when": null,
            "workflow_outputs": []
        },
        "4": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.2.1+galaxy0",
            "errors": null,
            "id": 4,
            "input_connections": {
                "adv|spliced_options|known_splice_gtf": {
                    "id": 2,
                    "output_name": "output"
                },
                "library|input_1": {
                    "id": 3,
                    "output_name": "trimmed_reads_pair1"
                },
                "library|input_2": {
                    "id": 3,
                    "output_name": "trimmed_reads_pair2"
                }
            },
            "inputs": [
                {
                    "description": "runtime parameter for tool HISAT2",
                    "name": "library"
                },
                {
                    "description": "runtime parameter for tool HISAT2",
                    "name": "library"
                }
            ],
            "label": null,
            "name": "HISAT2",
            "outputs": [
                {
                    "name": "output_alignments",
                    "type": "bam"
                }
            ],
            "position": {
                "bottom": 297.700008392334,
                "height": 172.1999969482422,
                "left": 719.0000152587891,
                "right": 879.0000610351562,
                "top": 125.5000114440918,
                "width": 160.0000457763672,
                "x": 719.0000152587891,
                "y": 125.5000114440918
            },
            "post_job_actions": {
                "HideDatasetActionoutput_alignments": {
                    "action_arguments": {},
                    "action_type": "HideDatasetAction",
                    "output_name": "output_alignments"
                }
            },
            "tool_id": "toolshed.g2.bx.psu.edu/repos/iuc/hisat2/hisat2/2.2.1+galaxy0",
            "tool_shed_repository": {
                "changeset_revision": "6c19daec423d",
                "name": "hisat2",
                "owner": "iuc",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"adv\": {\"input_options\": {\"input_options_selector\": \"defaults\", \"__current_case__\": 0}, \"alignment_options\": {\"alignment_options_selector\": \"defaults\", \"__current_case__\": 0}, \"scoring_options\": {\"scoring_options_selector\": \"defaults\", \"__current_case__\": 0}, \"spliced_options\": {\"spliced_options_selector\": \"advanced\", \"__current_case__\": 1, \"canonical_penalty\": \"0\", \"noncanonical_penalty\": \"12\", \"function_type\": \"G\", \"constant_term\": \"-8.0\", \"coefficient\": \"1.0\", \"nc_function_type\": \"G\", \"nc_constant_term\": \"-8.0\", \"nc_coefficient\": \"1.0\", \"min_intron\": \"20\", \"max_intron\": \"500000\", \"no_spliced_alignment_options\": {\"no_spliced_alignment\": \"\", \"__current_case__\": 1}, \"known_splice_gtf\": {\"__class__\": \"RuntimeValue\"}, \"tma\": \"\", \"notmplen\": false, \"novel_splicesite_outfile\": false}, \"reporting_options\": {\"reporting_options_selector\": \"defaults\", \"__current_case__\": 0}, \"output_options\": {\"output_options_selector\": \"defaults\", \"__current_case__\": 0}, \"sam_options\": {\"sam_options_selector\": \"defaults\", \"__current_case__\": 0}, \"other_options\": {\"other_options_selector\": \"defaults\", \"__current_case__\": 0}}, \"library\": {\"type\": \"paired\", \"__current_case__\": 1, \"input_1\": {\"__class__\": \"RuntimeValue\"}, \"input_2\": {\"__class__\": \"RuntimeValue\"}, \"rna_strandness\": \"\", \"paired_options\": {\"paired_options_selector\": \"advanced\", \"__current_case__\": 1, \"fr_rf_ff\": \"--fr\", \"no_mixed\": false, \"no_discordant\": false}}, \"reference_genome\": {\"source\": \"indexed\", \"__current_case__\": 0, \"index\": \"mm39\"}, \"sum\": {\"new_summary\": false, \"summary_file\": false}, \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "2.2.1+galaxy0",
            "type": "tool",
            "uuid": "1473469c-ede9-4423-b02e-88bf6e261a07",
            "when": null,
            "workflow_outputs": []
        },
        "5": {
            "annotation": "",
            "content_id": "toolshed.g2.bx.psu.edu/repos/lparsons/htseq_count/htseq_count/0.9.1+galaxy1",
            "errors": null,
            "id": 5,
            "input_connections": {
                "gfffile": {
                    "id": 2,
                    "output_name": "output"
                },
                "samfile": {
                    "id": 4,
                    "output_name": "output_alignments"
                }
            },
            "inputs": [
                {
                    "description": "runtime parameter for tool htseq-count",
                    "name": "gfffile"
                },
                {
                    "description": "runtime parameter for tool htseq-count",
                    "name": "samfile"
                }
            ],
            "label": null,
            "name": "htseq-count",
            "outputs": [
                {
                    "name": "counts",
                    "type": "tabular"
                },
                {
                    "name": "othercounts",
                    "type": "tabular"
                }
            ],
            "position": {
                "bottom": 447.70002365112305,
                "height": 172.20001220703125,
                "left": 997.0000457763672,
                "right": 1157.0000457763672,
                "top": 275.5000114440918,
                "width": 160,
                "x": 997.0000457763672,
                "y": 275.5000114440918
            },
            "post_job_actions": {},
            "tool_id": "toolshed.g2.bx.psu.edu/repos/lparsons/htseq_count/htseq_count/0.9.1+galaxy1",
            "tool_shed_repository": {
                "changeset_revision": "916cb26bd9d3",
                "name": "htseq_count",
                "owner": "lparsons",
                "tool_shed": "toolshed.g2.bx.psu.edu"
            },
            "tool_state": "{\"advanced_options\": {\"advanced_options_selector\": \"simple\", \"__current_case__\": 0}, \"featuretype\": \"exon\", \"gfffile\": {\"__class__\": \"RuntimeValue\"}, \"idattr\": \"gene_id\", \"minaqual\": \"10\", \"mode\": \"union\", \"samfile\": {\"__class__\": \"RuntimeValue\"}, \"stranded\": \"no\", \"__page__\": null, \"__rerun_remap_job_id__\": null}",
            "tool_version": "0.9.1+galaxy1",
            "type": "tool",
            "uuid": "32bf3d32-2f82-4a24-82ee-e942e42b014b",
            "when": null,
            "workflow_outputs": [
                {
                    "label": "htseq-count on input dataset(s) (no feature)",
                    "output_name": "othercounts",
                    "uuid": "0191dc1b-b9d5-42a3-80de-313472dc4bd0"
                },
                {
                    "label": null,
                    "output_name": "counts",
                    "uuid": "5dd577bf-7b48-4728-8f69-a6d8bffaae3c"
                }
            ]
        }
    },
    "tags": [],
    "uuid": "3054f1a8-8120-4221-8a68-772d88bf1a83",
    "version": 3
}
